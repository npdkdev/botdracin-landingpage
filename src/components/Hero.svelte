<script>
    import { PlayCircle, Check, LayoutDashboard, ArrowDownLeft, Users } from 'lucide-svelte';
    import { onMount, onDestroy } from 'svelte';

    let activeUsers = 0;
    let totalRevenue = 0;
    let uptime = 0;
    
    // Store timer references for cleanup
    let timers = [];
    
    // Configuration constants
    const ANIMATION_CONFIG = {
        DURATION: 2000,
        FRAME_RATE: 16,
        INITIAL_DELAY: 800,
        STATS: {
            ACTIVE_USERS: 1240,
            TOTAL_REVENUE: 50,
            UPTIME: 99.9
        }
    };

    function animateCounter(target, setter, duration = ANIMATION_CONFIG.DURATION) {
        const start = 0;
        const increment = target / (duration / ANIMATION_CONFIG.FRAME_RATE);
        let current = 0;
        
        const timer = setInterval(() => {
            current += increment;
            if (current >= target) {
                setter(target);
                clearInterval(timer);
                // Remove from timers array
                timers = timers.filter(t => t !== timer);
            } else {
                setter(Math.floor(current));
            }
        }, ANIMATION_CONFIG.FRAME_RATE);
        
        // Store timer for cleanup
        timers.push(timer);
        return timer;
    }

    onMount(() => {
        setTimeout(() => {
            animateCounter(ANIMATION_CONFIG.STATS.ACTIVE_USERS, (val) => activeUsers = val);
            animateCounter(ANIMATION_CONFIG.STATS.TOTAL_REVENUE, (val) => totalRevenue = val);
            animateCounter(ANIMATION_CONFIG.STATS.UPTIME, (val) => uptime = val);
        }, ANIMATION_CONFIG.INITIAL_DELAY);
    });
    
    onDestroy(() => {
        // Clean up all timers
        timers.forEach(timer => clearInterval(timer));
        timers = [];
    });
</script>

<section class="min-h-screen flex flex-col items-center justify-center pt-28 px-4 text-center relative z-10">
    
    <div class="max-w-5xl mx-auto flex flex-col items-center">
        <div class="reveal delay-100 inline-flex items-center gap-2 px-4 py-2 rounded-full glass-panel border border-white/10 hover:bg-white/5 transition-all cursor-default mb-10">
            <span class="w-2 h-2 rounded-full bg-green-400 animate-pulse shadow-[0_0_15px_#4ade80]"></span>
            <span class="text-[11px] font-bold tracking-[0.2em] uppercase text-white/60">iOS 26 Concept Ready</span>
        </div>

        <h1 class="reveal delay-200 heading-xl text-7xl md:text-9xl lg:text-[10rem] mb-8">
            Bisnis Streaming <br>
            <span class="animated-gradient-text">Tanpa Coding.</span>
        </h1>
        
        <p class="reveal delay-300 text-lg md:text-xl text-slate-400 max-w-2xl mx-auto mb-12 leading-relaxed font-light">
            Bot Telegram, Mini App, dan Admin Panel dalam satu ekosistem. <br>
            Otomatisasi 100% dari pembayaran hingga membership.
        </p>

        <!-- Floating Stat Cards -->
        <div class="reveal delay-300 absolute top-32 left-4 md:left-12 lg:left-24 hidden lg:block">
            <div class="glass-panel rounded-2xl p-4 border border-white/10 backdrop-blur-xl bg-black/40 shadow-2xl hover:scale-105 transition-transform duration-500">
                <div class="text-xs text-white/50 uppercase tracking-wider mb-1">Active Users</div>
                <div class="text-3xl font-bold text-white mb-1">{activeUsers.toLocaleString()}+</div>
                <div class="text-xs text-green-400 flex items-center gap-1">
                    <Users class="w-3 h-3" /> Growing Daily
                </div>
            </div>
        </div>

        <div class="reveal delay-400 absolute top-48 right-4 md:right-12 lg:right-24 hidden lg:block">
            <div class="glass-panel rounded-2xl p-4 border border-white/10 backdrop-blur-xl bg-black/40 shadow-2xl hover:scale-105 transition-transform duration-500">
                <div class="text-xs text-white/50 uppercase tracking-wider mb-1">Total Revenue</div>
                <div class="text-3xl font-bold text-white mb-1">Rp {totalRevenue}M+</div>
                <div class="text-xs text-green-400 flex items-center gap-1">
                    <ArrowDownLeft class="w-3 h-3 rotate-180" /> +12.5% Growth
                </div>
            </div>
        </div>

        <div class="reveal delay-500 absolute top-[28rem] left-8 md:left-20 hidden lg:block">
            <div class="glass-panel rounded-2xl p-4 border border-white/10 backdrop-blur-xl bg-black/40 shadow-2xl hover:scale-105 transition-transform duration-500">
                <div class="text-xs text-white/50 uppercase tracking-wider mb-1">Uptime</div>
                <div class="text-3xl font-bold text-white mb-1">{uptime.toFixed(1)}%</div>
                <div class="text-xs text-green-400 flex items-center gap-1">
                    <Check class="w-3 h-3" /> 24/7 Reliable
                </div>
            </div>
        </div>

        <!-- Floating Feature Badges -->
        <div class="absolute top-40 right-8 float-badge" style="animation-delay: 0s;">
            <div class="px-4 py-2 rounded-full glass-panel border border-emerald-500/30 bg-emerald-500/10 text-emerald-300 text-xs font-bold tracking-wide flex items-center gap-2 shadow-lg">
                Auto QRIS <Check class="w-3 h-3" />
            </div>
        </div>

        <div class="absolute top-[22rem] right-16 float-badge" style="animation-delay: 1s;">
            <div class="px-4 py-2 rounded-full glass-panel border border-blue-500/30 bg-blue-500/10 text-blue-300 text-xs font-bold tracking-wide flex items-center gap-2 shadow-lg">
                Real-time Analytics <Check class="w-3 h-3" />
            </div>
        </div>

        <div class="absolute top-[26rem] left-12 float-badge" style="animation-delay: 0.5s;">
            <div class="px-4 py-2 rounded-full glass-panel border border-purple-500/30 bg-purple-500/10 text-purple-300 text-xs font-bold tracking-wide flex items-center gap-2 shadow-lg">
                Multi-Bank Support <Check class="w-3 h-3" />
            </div>
        </div>

        <div class="absolute top-64 left-24 float-badge" style="animation-delay: 1.5s;">
            <div class="px-4 py-2 rounded-full glass-panel border border-pink-500/30 bg-pink-500/10 text-pink-300 text-xs font-bold tracking-wide flex items-center gap-2 shadow-lg">
                24/7 Automation <Check class="w-3 h-3" />
            </div>
        </div>

        <div class="absolute top-56 right-32 float-badge hidden xl:block" style="animation-delay: 2s;">
            <div class="px-4 py-2 rounded-full glass-panel border border-cyan-500/30 bg-cyan-500/10 text-cyan-300 text-xs font-bold tracking-wide flex items-center gap-2 shadow-lg">
                Instant Setup <Check class="w-3 h-3" />
            </div>
        </div>

        <div class="absolute top-[30rem] right-8 float-badge hidden xl:block" style="animation-delay: 0.8s;">
            <div class="px-4 py-2 rounded-full glass-panel border border-amber-500/30 bg-amber-500/10 text-amber-300 text-xs font-bold tracking-wide flex items-center gap-2 shadow-lg">
                Zero Code Required <Check class="w-3 h-3" />
            </div>
        </div>

        <div class="reveal delay-300 flex flex-col sm:flex-row gap-5 w-full justify-center mb-24 relative z-10">
            <a href="https://t.me/NpDkProjects" target="_blank" rel="noopener noreferrer" class="relative btn-modern btn-primary px-12 py-5 text-base uppercase tracking-widest shadow-xl hover-shine font-bold text-center">
                <span class="pulse-ring"></span>
                Mulai Sekarang
            </a>
            <a href="https://t.me/NpDkProjects" target="_blank" rel="noopener noreferrer" class="btn-modern glass-panel px-12 py-5 text-base uppercase tracking-widest flex items-center justify-center gap-3 hover:bg-white/5 hover-shine border-2 border-white/20 font-bold">
                <PlayCircle class="w-5 h-5" />
                Lihat Demo
            </a>
        </div>


    </div>

    <!-- Floating Particles -->
    {#each Array(15) as _, i}
        <div 
            class="particle" 
            style="
                width: {Math.random() * 4 + 2}px; 
                height: {Math.random() * 4 + 2}px; 
                left: {Math.random() * 100}%; 
                top: {Math.random() * 100}%;
                animation-delay: {Math.random() * 20}s;
                animation-duration: {Math.random() * 10 + 15}s;
            "
        ></div>
    {/each}
</section>