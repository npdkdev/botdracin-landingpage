<script>
    import { Palette, MessageCircle, Sparkles, Wand2 } from 'lucide-svelte';
    
    let botName = 'DramaKu';
    let welcomeMessage = 'Halo! Cari drama apa hari ini?';
    let brandColor = '#8b5cf6';
    
    const presetColors = [
        { name: 'Purple', value: '#8b5cf6' },
        { name: 'Blue', value: '#3b82f6' },
        { name: 'Pink', value: '#ec4899' },
        { name: 'Emerald', value: '#10b981' },
        { name: 'Orange', value: '#f59e0b' },
        { name: 'Red', value: '#ef4444' }
    ];
    
    function hexToRgb(hex) {
        const result = /^#?([a-f\d]{2})([a-f\d]{2})([a-f\d]{2})$/i.exec(hex);
        return result ? {
            r: parseInt(result[1], 16),
            g: parseInt(result[2], 16),
            b: parseInt(result[3], 16)
        } : { r: 139, g: 92, b: 246 };
    }
    
    $: rgb = hexToRgb(brandColor);
</script>

<div class="flex flex-col md:flex-row-reverse items-stretch gap-16 reveal">
    <!-- Right Content -->
    <div class="flex-1 flex flex-col justify-center space-y-8">
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-violet-500/30 bg-violet-500/10 text-violet-400 text-[10px] font-bold tracking-widest uppercase w-fit">
            White Label Power
        </div>
        <h2 class="text-4xl md:text-6xl font-bold leading-tight text-white">
            Bot Anda, <br><span class="bg-gradient-to-r from-violet-400 to-fuchsia-500 bg-clip-text text-transparent">Brand Anda</span>.
        </h2>
        <p class="text-slate-400 text-lg leading-relaxed max-w-lg">
            Ganti nama bot, logo, warna brand, dan welcome message sesuka hati. 
            <strong class="text-violet-400">100% white label</strong> — user hanya lihat brand Anda, bukan kami.
        </p>
        
        <!-- Feature Highlights -->
        <div class="space-y-3 mt-4">
            <div class="flex items-center gap-3 text-sm group">
                <div class="w-8 h-8 rounded-lg bg-violet-500/10 border border-violet-500/20 flex items-center justify-center group-hover:bg-violet-500/20 transition-all">
                    <Palette class="w-4 h-4 text-violet-400" />
                </div>
                <span class="text-slate-300 font-medium group-hover:text-white transition-colors">
                    Custom Brand Colors & Logo
                </span>
            </div>
            <div class="flex items-center gap-3 text-sm group">
                <div class="w-8 h-8 rounded-lg bg-violet-500/10 border border-violet-500/20 flex items-center justify-center group-hover:bg-violet-500/20 transition-all">
                    <MessageCircle class="w-4 h-4 text-violet-400" />
                </div>
                <span class="text-slate-300 font-medium group-hover:text-white transition-colors">
                    Personalized Welcome Messages
                </span>
            </div>
            <div class="flex items-center gap-3 text-sm group">
                <div class="w-8 h-8 rounded-lg bg-violet-500/10 border border-violet-500/20 flex items-center justify-center group-hover:bg-violet-500/20 transition-all">
                    <Wand2 class="w-4 h-4 text-violet-400" />
                </div>
                <span class="text-slate-300 font-medium group-hover:text-white transition-colors">
                    Custom Commands & Branding
                </span>
            </div>
        </div>
    </div>

    <!-- Left Interactive Settings Panel -->
    <div class="flex-1 relative">
        <!-- Background Gradient -->
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_top_left,rgba(139,92,246,0.08),transparent_70%)] rounded-3xl"></div>
        
        <!-- Settings Panel -->
        <div class="relative glass-panel rounded-[2.5rem] p-8 border border-violet-500/20 shadow-[0_30px_60px_rgba(139,92,246,0.1)]">
            
            <!-- Header -->
            <div class="mb-8 pb-6 border-b border-white/10">
                <div class="flex items-center justify-between">
                    <h3 class="text-xl font-bold text-white">White Label Settings</h3>
                    <div class="px-3 py-1 rounded-full bg-violet-500/10 border border-violet-500/30 flex items-center gap-1.5">
                        <Sparkles class="w-3 h-3 text-violet-400" />
                        <span class="text-violet-400 text-xs font-bold">Pro</span>
                    </div>
                </div>
            </div>

            <!-- Settings Form -->
            <div class="space-y-6">
                
                <!-- Bot Name Input -->
                <div class="space-y-3">
                    <label class="text-sm font-bold text-slate-300 uppercase tracking-wider flex items-center gap-2">
                        <div class="w-1.5 h-1.5 rounded-full bg-violet-400"></div>
                        Bot Name
                    </label>
                    <input 
                        type="text" 
                        bind:value={botName}
                        placeholder="Enter bot name..."
                        maxlength="20"
                        class="w-full px-4 py-3.5 rounded-2xl bg-white/5 border border-white/10 text-white placeholder-slate-500 
                               focus:bg-white/8 focus:border-violet-500/50 focus:outline-none focus:ring-2 focus:ring-violet-500/20
                               transition-all duration-300 font-medium"
                    />
                    <div class="text-xs text-slate-500 flex items-center justify-between">
                        <span>This appears in user chats</span>
                        <span class="font-mono">{botName.length}/20</span>
                    </div>
                </div>

                <!-- Welcome Message Input -->
                <div class="space-y-3">
                    <label class="text-sm font-bold text-slate-300 uppercase tracking-wider flex items-center gap-2">
                        <div class="w-1.5 h-1.5 rounded-full bg-violet-400"></div>
                        Welcome Message
                    </label>
                    <textarea 
                        bind:value={welcomeMessage}
                        placeholder="Type your welcome message..."
                        maxlength="100"
                        rows="3"
                        class="w-full px-4 py-3.5 rounded-2xl bg-white/5 border border-white/10 text-white placeholder-slate-500 
                               focus:bg-white/8 focus:border-violet-500/50 focus:outline-none focus:ring-2 focus:ring-violet-500/20
                               transition-all duration-300 font-medium resize-none"
                    ></textarea>
                    <div class="text-xs text-slate-500 flex items-center justify-between">
                        <span>First message users see</span>
                        <span class="font-mono">{welcomeMessage.length}/100</span>
                    </div>
                </div>

                <!-- Brand Color Picker -->
                <div class="space-y-3">
                    <label class="text-sm font-bold text-slate-300 uppercase tracking-wider flex items-center gap-2">
                        <div class="w-1.5 h-1.5 rounded-full bg-violet-400"></div>
                        Brand Color
                    </label>
                    
                    <!-- Color Presets -->
                    <div class="grid grid-cols-6 gap-2">
                        {#each presetColors as preset}
                            <button
                                on:click={() => brandColor = preset.value}
                                class="aspect-square rounded-xl border-2 transition-all duration-300 hover:scale-110 relative group
                                       {brandColor === preset.value ? 'border-white/40 scale-105' : 'border-white/10 hover:border-white/30'}"
                                style="background: {preset.value}"
                                title={preset.name}
                            >
                                {#if brandColor === preset.value}
                                    <div class="absolute inset-0 rounded-xl bg-white/20 flex items-center justify-center">
                                        <div class="w-2 h-2 rounded-full bg-white"></div>
                                    </div>
                                {/if}
                                <div class="absolute -bottom-6 left-1/2 -translate-x-1/2 whitespace-nowrap text-[9px] text-slate-500 font-bold opacity-0 group-hover:opacity-100 transition-opacity">
                                    {preset.name}
                                </div>
                            </button>
                        {/each}
                    </div>

                    <!-- Custom Color Input -->
                    <div class="flex items-center gap-3 mt-4">
                        <div class="relative flex-1">
                            <input 
                                type="text" 
                                bind:value={brandColor}
                                placeholder="#8b5cf6"
                                maxlength="7"
                                class="w-full px-4 py-3 pl-12 rounded-2xl bg-white/5 border border-white/10 text-white placeholder-slate-500 
                                       focus:bg-white/8 focus:border-violet-500/50 focus:outline-none focus:ring-2 focus:ring-violet-500/20
                                       transition-all duration-300 font-mono text-sm"
                            />
                            <div 
                                class="absolute left-3 top-1/2 -translate-y-1/2 w-6 h-6 rounded-lg border-2 border-white/20 shadow-lg transition-all duration-300"
                                style="background: {brandColor}"
                            ></div>
                        </div>
                        <input 
                            type="color" 
                            bind:value={brandColor}
                            class="w-12 h-12 rounded-xl cursor-pointer border-2 border-white/10 hover:border-white/30 transition-all"
                            style="background: none"
                        />
                    </div>
                </div>
            </div>

            <!-- Divider -->
            <div class="my-8 border-t border-white/10"></div>

            <!-- Live Preview Section -->
            <div class="space-y-3">
                <div class="text-sm font-bold text-slate-300 uppercase tracking-wider flex items-center gap-2 mb-4">
                    <div class="w-1.5 h-1.5 rounded-full bg-emerald-400"></div>
                    Live Preview
                </div>
                
                <!-- Bot Profile Preview Card -->
                <div 
                    class="glass-panel-dark rounded-2xl p-6 border-2 transition-all duration-500 hover:scale-[1.02]"
                    style="border-color: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.3); 
                           box-shadow: 0 20px 40px rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.1)"
                >
                    <!-- Bot Avatar & Name -->
                    <div class="flex items-start gap-4 mb-6">
                        <div 
                            class="w-16 h-16 rounded-2xl flex items-center justify-center text-2xl font-black text-white border-2 shadow-lg transition-all duration-500"
                            style="background: linear-gradient(135deg, {brandColor}40, {brandColor}20);
                                   border-color: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.4);
                                   box-shadow: 0 10px 30px rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.3)"
                        >
                            {botName.charAt(0).toUpperCase()}
                        </div>
                        <div class="flex-1">
                            <h4 class="text-xl font-bold text-white mb-1 transition-all duration-300">
                                {botName || 'Your Bot'}
                            </h4>
                            <div class="flex items-center gap-2">
                                <div 
                                    class="w-2 h-2 rounded-full animate-pulse transition-all duration-500" 
                                    style="background: {brandColor}"
                                ></div>
                                <span class="text-xs text-slate-400 font-medium">Active Now</span>
                            </div>
                        </div>
                    </div>

                    <!-- Welcome Message Bubble -->
                    <div class="relative">
                        <div 
                            class="rounded-2xl rounded-tl-sm p-4 border transition-all duration-500"
                            style="background: linear-gradient(135deg, rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.15), rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.05));
                                   border-color: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.3)"
                        >
                            <p class="text-white text-sm leading-relaxed">
                                {welcomeMessage || 'Welcome to the bot!'}
                            </p>
                        </div>
                        <!-- Timestamp -->
                        <div class="mt-2 text-[10px] text-slate-500 font-medium">
                            Just now
                        </div>
                    </div>

                    <!-- Quick Actions Preview -->
                    <div class="mt-6 pt-6 border-t border-white/5">
                        <div class="grid grid-cols-2 gap-2">
                            <button 
                                class="px-4 py-2.5 rounded-xl border transition-all duration-300 hover:scale-[1.02] text-sm font-semibold"
                                style="background: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.1);
                                       border-color: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.3);
                                       color: {brandColor}"
                            >
                                Browse
                            </button>
                            <button 
                                class="px-4 py-2.5 rounded-xl border transition-all duration-300 hover:scale-[1.02] text-sm font-semibold"
                                style="background: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.1);
                                       border-color: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.3);
                                       color: {brandColor}"
                            >
                                VIP
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Brand Identity Info -->
                <div 
                    class="mt-4 p-4 rounded-xl border transition-all duration-500"
                    style="background: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.05);
                           border-color: rgba({rgb.r}, {rgb.g}, {rgb.b}, 0.2)"
                >
                    <div class="flex items-start gap-3">
                        <Sparkles class="w-5 h-5 flex-shrink-0 mt-0.5 transition-all duration-500" style="color: {brandColor}" />
                        <div class="text-xs text-slate-300 leading-relaxed">
                            User hanya lihat <strong class="font-bold" style="color: {brandColor}">"{botName}"</strong> — 
                            brand Anda 100%, bukan platform kami.
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Floating Decorative Elements -->
        <div 
            class="absolute -top-6 -left-6 w-32 h-32 rounded-full blur-3xl opacity-50 animate-pulse transition-all duration-1000" 
            style="background: {brandColor}40; animation-duration: 4s;"
        ></div>
        <div 
            class="absolute -bottom-4 -right-4 w-24 h-24 rounded-full blur-2xl opacity-40 animate-pulse transition-all duration-1000" 
            style="background: {brandColor}30; animation-duration: 6s; animation-delay: 2s;"
        ></div>
    </div>
</div>
