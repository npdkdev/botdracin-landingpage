<script>
    import { Sparkles, Wand2, Bot, Loader2 } from 'lucide-svelte';
    import { marked } from 'marked';
    import DOMPurify from 'dompurify';
    import Toast from './Toast.svelte';

    let niche = '';
    let isLoading = false;
    let result = '';
    let showResult = false;
    let resultElement;
    
    // Toast notification state
    let toastVisible = false;
    let toastMessage = '';
    let toastType = 'info';
    
    // Get API key from environment variable
    const apiKey = import.meta.env.VITE_GEMINI_API_KEY || '';
    
    // Configuration constants
    const CONFIG = {
        API_TIMEOUT: 30000, // 30 seconds
        MIN_NICHE_LENGTH: 3,
        MAX_NICHE_LENGTH: 100,
        SCROLL_DELAY: 100
    };

    function showNotification(type, message) {
        toastType = type;
        toastMessage = message;
        toastVisible = true;
    }

    function validateNiche(input) {
        const trimmed = input.trim();
        
        if (trimmed.length === 0) {
            return { valid: false, error: 'Silakan masukkan niche film terlebih dahulu!' };
        }
        
        if (trimmed.length < CONFIG.MIN_NICHE_LENGTH) {
            return { valid: false, error: `Niche minimal ${CONFIG.MIN_NICHE_LENGTH} karakter` };
        }
        
        if (trimmed.length > CONFIG.MAX_NICHE_LENGTH) {
            return { valid: false, error: `Niche maksimal ${CONFIG.MAX_NICHE_LENGTH} karakter` };
        }
        
        // Check for suspicious patterns (XSS attempts)
        if (/<script|javascript:|on\w+=/i.test(trimmed)) {
            return { valid: false, error: 'Input tidak valid' };
        }
        
        return { valid: true, value: trimmed };
    }

    async function generateStrategy() {
        // Validate input
        const validation = validateNiche(niche);
        if (!validation.valid) {
            showNotification('error', validation.error);
            return;
        }
        
        niche = validation.value;

        if (!apiKey) {
            showNotification('error', 'API Key belum dikonfigurasi. Silakan set VITE_GEMINI_API_KEY di file .env');
            return;
        }

        isLoading = true;
        result = '';
        showResult = false;

        const prompt = `
            Bertindaklah sebagai Konsultan Bisnis Digital profesional. 
            Saya ingin membuat Bisnis Streaming Film di Telegram menggunakan "VIP Bot".
            
            Niche/Topik saya adalah: "${niche}".
            
            Berikan saya strategi singkat dalam format Markdown (tanpa code block):
            1. **Target Audience**: Siapa yang akan menonton ini?
            2. **Strategi Marketing**: 2 ide unik untuk mempromosikan niche ini.
            3. **Proyeksi Harga**: Rekomendasi harga paket VIP mingguan & bulanan yang cocok untuk niche ini.
            
            Gunakan bahasa Indonesia yang persuasif, emoji yang relevan, dan format yang rapi. Buat jawaban yang singkat dan padat (maksimal 150 kata).
        `;

        // AbortController for timeout
        const controller = new AbortController();
        const timeoutId = setTimeout(() => controller.abort(), CONFIG.API_TIMEOUT);

        try {
            const response = await fetch(
                `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`, 
                {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify({
                        contents: [{
                            parts: [{
                                text: prompt
                            }]
                        }]
                    }),
                    signal: controller.signal
                }
            );

            clearTimeout(timeoutId);

            if (!response.ok) {
                throw new Error(`HTTP ${response.status}: ${response.statusText}`);
            }

            const data = await response.json();
            
            if (data.error) {
                throw new Error(data.error.message);
            }

            const aiText = data.candidates?.[0]?.content?.parts?.[0]?.text;
            
            if (!aiText) {
                throw new Error('Tidak ada respons dari AI');
            }
            
            // Handle possible promise return from marked.parse
            const parsed = marked.parse(aiText);
            const htmlContent = parsed instanceof Promise ? await parsed : parsed;
            
            // CRITICAL: Sanitize HTML to prevent XSS
            result = DOMPurify.sanitize(htmlContent);
            
            showResult = true;
            
            // Scroll to result after render
            setTimeout(() => {
                resultElement?.scrollIntoView({ behavior: 'smooth', block: 'center' });
            }, CONFIG.SCROLL_DELAY);
            
            showNotification('success', 'Strategi berhasil dibuat!');

        } catch (error) {
            clearTimeout(timeoutId);
            
            // Conditional logging (only in development)
            if (import.meta.env.DEV) {
                console.error('AI Generation Error:', error);
            }
            
            // Better error messages
            if (error.name === 'AbortError') {
                showNotification('error', 'Request timeout - silakan coba lagi');
            } else if (error.message.includes('HTTP 429')) {
                showNotification('error', 'Terlalu banyak permintaan - tunggu sebentar');
            } else if (error.message.includes('HTTP 401')) {
                showNotification('error', 'API Key tidak valid');
            } else {
                showNotification('error', 'Maaf, terjadi kesalahan: ' + error.message);
            }
        } finally {
            isLoading = false;
        }
    }
</script>

<Toast bind:visible={toastVisible} message={toastMessage} type={toastType} />

<section id="ai-planner" class="py-32 px-4 relative z-10">
    <div class="max-w-4xl mx-auto reveal">
        <div class="glass-panel rounded-[3rem] p-10 md:p-16 relative overflow-hidden border-indigo-500/30">
            <!-- Decorative BG -->
            <div class="absolute top-0 right-0 p-12 opacity-40 pointer-events-none blur-3xl">
                <div class="w-64 h-64 bg-indigo-500 rounded-full"></div>
            </div>
            
            <div class="relative z-10">
                <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-indigo-400/30 bg-indigo-500/10 text-indigo-300 text-xs font-bold tracking-wider uppercase mb-6">
                    <Sparkles class="w-3 h-3" /> Gemini AI Powered
                </div>
                <h2 class="text-4xl md:text-5xl font-bold mb-6 text-white">AI Business Planner</h2>
                <p class="text-slate-400 text-lg mb-10 max-w-xl">
                    Bingung mulai dari mana? Masukkan niche film Anda (misal: "Drama Korea" atau "Anime"), AI akan merancang strategi bisnis instan.
                </p>

                <div class="space-y-6 max-w-xl">
                    <div>
                        <label for="nicheInput" class="block text-xs font-bold uppercase tracking-widest text-slate-500 mb-3 ml-1">Target Niche</label>
                        <div class="flex flex-col sm:flex-row gap-4">
                            <input type="text" id="nicheInput" placeholder="Contoh: Film Horor Jadul..." 
                                bind:value={niche}
                                class="flex-1 modern-input px-6 py-4 placeholder-slate-600">
                            <button on:click={generateStrategy} disabled={isLoading} id="generateBtn" class="btn-modern btn-primary px-8 py-4 whitespace-nowrap flex items-center justify-center gap-2 hover-shine">
                                {#if isLoading}
                                    <span>Menganalisa...</span>
                                    <Loader2 class="w-4 h-4 animate-spin" />
                                {:else}
                                    <span>Analisa</span>
                                    <Wand2 class="w-4 h-4" />
                                {/if}
                            </button>
                        </div>
                    </div>

                    <!-- Result Area -->
                    {#if showResult}
                        <div bind:this={resultElement} id="aiResult">
                            <div class="glass-panel-dark rounded-3xl p-8 mt-8 border border-indigo-500/30 animate-fade-in-up">
                                <div class="flex items-center gap-3 mb-6 border-b border-white/10 pb-4">
                                    <div class="w-8 h-8 rounded-full bg-indigo-500 flex items-center justify-center shadow-[0_0_15px_#6366f1]">
                                        <Bot class="w-4 h-4 text-white" />
                                    </div>
                                    <span class="font-bold text-indigo-300 tracking-wide">Strategi Bisnis Gemini</span>
                                </div>
                                <div class="ai-content text-sm md:text-base leading-relaxed text-white/80">
                                    {@html result}
                                </div>
                            </div>
                        </div>
                    {/if}
                </div>
            </div>
        </div>
    </div>
</section>