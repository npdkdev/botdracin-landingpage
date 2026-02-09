<script>
    import { Zap, Send } from 'lucide-svelte';
</script>

<footer class="py-20 mt-20 relative border-t border-white/5 bg-black/40 backdrop-blur-xl z-10 overflow-hidden">
    <div class="max-w-7xl mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-12 mb-16">
            
            <div class="space-y-6">
                <div class="flex items-center gap-2">
                    <Zap class="w-8 h-8 text-indigo-400" />
                    <span class="text-xl font-bold text-white">VIP Bot</span>
                </div>
                <p class="text-slate-400 text-sm leading-relaxed">
                    Platform Streaming #1<br/>
                    Automasi konten cerdas untuk creator masa depan.
                </p>
            </div>

            <div>
                <h4 class="text-white font-semibold mb-6 text-sm uppercase tracking-wider">Hubungi Kami</h4>
                <a href="https://t.me/NpDkProjects" target="_blank" rel="noopener noreferrer"
                   class="inline-flex items-center gap-2 text-slate-400 hover:text-white transition-colors duration-300 group">
                    <Send class="w-5 h-5 group-hover:translate-x-0.5 transition-transform" />
                    <span class="text-sm">Telegram: @NpDkProjects</span>
                </a>
            </div>
        </div>

        <div class="pt-8 border-t border-white/5 flex flex-col md:flex-row items-center justify-between gap-4">
            <p class="text-slate-600 text-xs">
                &copy; 2026 VIP Bot. All rights reserved.
            </p>
            <div class="flex items-center gap-2">
                <div class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></div>
                <span class="text-slate-500 text-xs">Status: Operational</span>
            </div>
        </div>
    </div>
</footer>
