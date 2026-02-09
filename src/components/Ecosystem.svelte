<script>
    import { Bot, Smartphone, LayoutGrid } from 'lucide-svelte';
</script>

<section id="ecosystem" class="py-20 px-4 relative z-10">
    <div class="max-w-6xl mx-auto">
        
        <!-- Section Header -->
        <div class="mb-16 md:flex md:items-end md:justify-between reveal">
            <h2 class="text-4xl md:text-5xl font-bold max-w-md leading-tight">
            <span class="bg-gradient-to-r from-slate-400 via-white to-white bg-clip-text text-transparent">Ekosistem</span> <br>
            <span class="bg-gradient-to-r from-slate-500 via-slate-300 to-white bg-clip-text text-transparent">All-in-One.</span>
        </h2>
            <p class="text-slate-400 mt-4 md:mt-0 text-right max-w-xs">3 platform canggih yang bekerja sinkron untuk bisnis Anda.</p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6 relative">
            
            <!-- Connecting Lines SVG -->
            <svg class="absolute inset-0 w-full h-full pointer-events-none hidden md:block" style="z-index: 0;">
                <defs>
                    <linearGradient id="lineGradient1" x1="0%" y1="0%" x2="100%" y2="0%">
                        <stop offset="0%" style="stop-color:rgb(217,70,239);stop-opacity:0.3" />
                        <stop offset="100%" style="stop-color:rgb(99,102,241);stop-opacity:0.3" />
                    </linearGradient>
                    <linearGradient id="lineGradient2" x1="0%" y1="0%" x2="100%" y2="0%">
                        <stop offset="0%" style="stop-color:rgb(99,102,241);stop-opacity:0.3" />
                        <stop offset="100%" style="stop-color:rgb(34,211,238);stop-opacity:0.3" />
                    </linearGradient>
                </defs>
                
                <!-- Line 1->2 -->
                <path d="M 320 180 Q 400 180, 480 180" stroke="url(#lineGradient1)" stroke-width="2" fill="none" stroke-dasharray="8 4" opacity="0.6">
                    <animate attributeName="stroke-dashoffset" from="0" to="-12" dur="1.5s" repeatCount="indefinite" />
                </path>
                
                <!-- Line 2->3 -->
                <path d="M 800 180 Q 880 180, 960 180" stroke="url(#lineGradient2)" stroke-width="2" fill="none" stroke-dasharray="8 4" opacity="0.6">
                    <animate attributeName="stroke-dashoffset" from="0" to="-12" dur="1.5s" repeatCount="indefinite" />
                </path>
                
                <!-- Animated Dots on Line 1 -->
                <circle r="3" fill="rgb(217,70,239)" opacity="0.8">
                    <animateMotion dur="3s" repeatCount="indefinite">
                        <mpath href="#path1"/>
                    </animateMotion>
                </circle>
                <path id="path1" d="M 320 180 Q 400 180, 480 180" fill="none" stroke="none"/>
                
                <!-- Animated Dots on Line 2 -->
                <circle r="3" fill="rgb(99,102,241)" opacity="0.8">
                    <animateMotion dur="3s" repeatCount="indefinite">
                        <mpath href="#path2"/>
                    </animateMotion>
                </circle>
                <path id="path2" d="M 800 180 Q 880 180, 960 180" fill="none" stroke="none"/>
            </svg>
            
            <!-- Card 1: Telegram Bot -->
            <div class="glass-panel rounded-3xl p-8 relative overflow-hidden group reveal hover:scale-[1.02] hover:-translate-y-3 transition-all duration-500 border border-white/5 hover:border-fuchsia-500/30 hover:shadow-2xl hover:shadow-fuchsia-500/20">
                <!-- Huge Watermark Number -->
                <div class="absolute -right-6 -top-8 text-[18rem] font-black text-fuchsia-500/5 select-none pointer-events-none leading-none">1</div>
                
                <!-- Shimmer Effect -->
                <div class="absolute inset-0 opacity-0 group-hover:opacity-100 transition-opacity duration-700">
                    <div class="absolute inset-0 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 bg-gradient-to-r from-transparent via-white/10 to-transparent"></div>
                </div>
                
                <div class="absolute -right-10 -top-10 w-40 h-40 bg-fuchsia-500/10 rounded-full blur-[60px] group-hover:bg-fuchsia-500/20 transition-colors duration-500"></div>
                <div class="relative z-10">
                    <div class="w-16 h-16 rounded-2xl bg-fuchsia-500/10 border border-fuchsia-500/20 flex items-center justify-center mb-8 group-hover:scale-110 transition-transform duration-300 shadow-lg shadow-fuchsia-500/5 group-hover:shadow-2xl group-hover:shadow-fuchsia-500/40">
                        <Bot class="w-8 h-8 text-fuchsia-400 group-hover:text-fuchsia-300 transition-colors drop-shadow-[0_0_12px_rgba(232,121,249,0.6)]" />
                    </div>
                    <h3 class="text-2xl font-bold mb-2 text-white flex items-center gap-3">
                        <span class="text-fuchsia-500/50 text-4xl font-black -mt-1">1</span>
                        Telegram Bot
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse shadow-lg shadow-emerald-400/50"></span>
                    </h3>
                    <p class="text-slate-400 text-sm mb-6 pl-9">Interface utama untuk pelanggan.</p>
                    <ul class="space-y-3 text-sm pl-2">
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-fuchsia-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">Deep Link</strong> <span class="text-slate-400 leading-relaxed">Share link langsung ke film tanpa ribet.</span></span>
                        </li>
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-fuchsia-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">Inline Search</strong> <span class="text-slate-400 leading-relaxed">Cari film di chat manapun dengan cepat.</span></span>
                        </li>
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-fuchsia-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">VIP System</strong> <span class="text-slate-400 leading-relaxed">Auto-expire & proteksi konten premium.</span></span>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Card 2: Mini App Dashboard -->
            <div class="glass-panel rounded-3xl p-8 relative overflow-hidden group reveal delay-100 hover:scale-[1.02] hover:-translate-y-3 transition-all duration-500 border border-white/5 hover:border-indigo-500/30 hover:shadow-2xl hover:shadow-indigo-500/20">
                <div class="absolute -right-6 -top-8 text-[18rem] font-black text-indigo-500/5 select-none pointer-events-none leading-none">2</div>
                
                <div class="absolute inset-0 opacity-0 group-hover:opacity-100 transition-opacity duration-700">
                    <div class="absolute inset-0 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 bg-gradient-to-r from-transparent via-white/10 to-transparent"></div>
                </div>
                
                <div class="absolute -right-10 -top-10 w-40 h-40 bg-indigo-500/10 rounded-full blur-[60px] group-hover:bg-indigo-500/20 transition-colors duration-500"></div>
                <div class="relative z-10">
                    <div class="w-16 h-16 rounded-2xl bg-indigo-500/10 border border-indigo-500/20 flex items-center justify-center mb-8 group-hover:scale-110 transition-transform duration-300 shadow-lg shadow-indigo-500/5 group-hover:shadow-2xl group-hover:shadow-indigo-500/40">
                        <Smartphone class="w-8 h-8 text-indigo-400 group-hover:text-indigo-300 transition-colors drop-shadow-[0_0_12px_rgba(129,140,248,0.6)]" />
                    </div>
                    <h3 class="text-2xl font-bold mb-2 text-white flex items-center gap-3">
                        <span class="text-indigo-500/50 text-4xl font-black -mt-1">2</span>
                        Mini App
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse shadow-lg shadow-emerald-400/50"></span>
                    </h3>
                    <p class="text-slate-400 text-sm mb-6 pl-9">Web app embedded di dalam Telegram.</p>
                    <ul class="space-y-3 text-sm pl-2">
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-indigo-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">Grafik & VIP</strong> <span class="text-slate-400 leading-relaxed">Cek statistik pendapatan, grafik harian, & sisa durasi VIP.</span></span>
                        </li>
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-indigo-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">Smart Payment</strong> <span class="text-slate-400 leading-relaxed">Auto-generate QRIS & verifikasi pembayaran otomatis.</span></span>
                        </li>
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-indigo-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">Withdrawal ke Bank</strong> <span class="text-slate-400 leading-relaxed">Tarik komisi referral ke semua bank & e-wallet.</span></span>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Card 3: Admin Web Panel -->
            <div class="glass-panel rounded-3xl p-8 relative overflow-hidden group reveal delay-200 hover:scale-[1.02] hover:-translate-y-3 transition-all duration-500 border border-white/5 hover:border-cyan-500/30 hover:shadow-2xl hover:shadow-cyan-500/20">
                <div class="absolute -right-6 -top-8 text-[18rem] font-black text-cyan-500/5 select-none pointer-events-none leading-none">3</div>
                
                <div class="absolute inset-0 opacity-0 group-hover:opacity-100 transition-opacity duration-700">
                    <div class="absolute inset-0 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 bg-gradient-to-r from-transparent via-white/10 to-transparent"></div>
                </div>
                
                <div class="absolute -right-10 -top-10 w-40 h-40 bg-cyan-500/10 rounded-full blur-[60px] group-hover:bg-cyan-500/20 transition-colors duration-500"></div>
                <div class="relative z-10">
                    <div class="w-16 h-16 rounded-2xl bg-cyan-500/10 border border-cyan-500/20 flex items-center justify-center mb-8 group-hover:scale-110 transition-transform duration-300 shadow-lg shadow-cyan-500/5 group-hover:shadow-2xl group-hover:shadow-cyan-500/40">
                        <LayoutGrid class="w-8 h-8 text-cyan-400 group-hover:text-cyan-300 transition-colors drop-shadow-[0_0_12px_rgba(34,211,238,0.6)]" />
                    </div>
                    <h3 class="text-2xl font-bold mb-2 text-white flex items-center gap-3">
                        <span class="text-cyan-500/50 text-4xl font-black -mt-1">3</span>
                        Admin Panel
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse shadow-lg shadow-emerald-400/50"></span>
                    </h3>
                    <p class="text-slate-400 text-sm mb-6 pl-9">Kendali penuh bisnis di tangan Anda.</p>
                    <ul class="space-y-3 text-sm pl-2">
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-pink-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">Movie Library</strong> <span class="text-slate-400 leading-relaxed">Upload, edit, & kelola database film.</span></span>
                        </li>
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-pink-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">Finance</strong> <span class="text-slate-400 leading-relaxed">Pantau revenue & transaksi harian.</span></span>
                        </li>
                        <li class="flex items-start gap-3 group/item">
                            <span class="w-1.5 h-1.5 rounded-full bg-pink-500 mt-2 group-hover/item:scale-150 transition-transform"></span>
                            <span><strong class="text-white block text-base mb-0.5">User Mgmt</strong> <span class="text-slate-400 leading-relaxed">Kelola user, banned, atau beri bonus.</span></span>
                        </li>
                    </ul>
                </div>
            </div>

        </div>
    </div>
</section>