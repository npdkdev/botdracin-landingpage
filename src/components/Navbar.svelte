<script>
    import { Play } from 'lucide-svelte';
    
    let scrollY = 0;
    $: isScrolled = scrollY > 50;
</script>

<svelte:window bind:scrollY />

<nav 
    class="fixed left-1/2 -translate-x-1/2 z-[100] transition-all duration-500 ease-in-out {isScrolled ? 'w-full max-w-none top-0' : 'w-[95%] max-w-2xl top-6'}"
>
    <div 
        class="glass-panel flex items-center justify-between shadow-2xl transition-all duration-500 ease-in-out {isScrolled ? 'rounded-none border-b border-white/5 bg-black/80 backdrop-blur-xl shadow-lg p-3 pl-8 pr-3' : 'rounded-full border border-white/10 bg-black/20 backdrop-blur-md p-2 pl-6 pr-2'}"
    >
        <div class="flex items-center gap-3">
            <div class="w-8 h-8 rounded-full bg-white flex items-center justify-center shadow-[0_0_20px_rgba(255,255,255,0.4)] transition-transform duration-500 ease-in-out {isScrolled ? 'scale-95' : 'scale-100'}">
                <Play class="w-3.5 h-3.5 text-black fill-black ml-0.5" />
            </div>
            <span class="font-bold text-sm tracking-wide text-white">VIP Bot</span>
        </div>
        
        <div class="hidden md:flex items-center gap-6 text-xs font-medium text-slate-400">
            <a href="#ecosystem" class="hover:text-white transition-colors">Ekosistem</a>
            <a href="#features" class="hover:text-white transition-colors">Fitur</a>
            <a href="#rental-pricing" class="hover:text-white transition-colors">Paket</a>
            <a href="#pricing" class="hover:text-white transition-colors">Bisnis</a>
            <a href="#faq" class="hover:text-white transition-colors">FAQ</a>
        </div>

        <a href="https://t.me/NpDkProjects" target="_blank" rel="noopener noreferrer" class="btn-modern btn-primary px-6 py-2.5 text-xs font-bold tracking-wider uppercase flex items-center gap-2 hover-shine">
            Beli Sekarang
        </a>
    </div>
</nav>