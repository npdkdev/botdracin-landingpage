<script>
    import { MessageSquarePlus, CheckCircle2, Bell, ArrowRight, Sparkles, Clock, TrendingUp } from 'lucide-svelte';
    
    let step1Hovered = false;
    let step2Hovered = false;
    let step3Hovered = false;
</script>

<div class="flex flex-col md:flex-row items-stretch gap-12 reveal">
    <div class="flex-1 flex flex-col justify-center space-y-8">
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-emerald-500/30 bg-emerald-500/10 text-emerald-400 text-[10px] font-bold tracking-widest uppercase w-fit">
            User Engagement
        </div>
        <h2 class="text-4xl md:text-6xl font-bold leading-tight text-white">Content On <br>Demand.</h2>
        <p class="text-slate-400 text-lg leading-relaxed max-w-lg">
            User bisa request film yang diinginkan. Request masuk ke admin panel Anda. 
            Tingkatkan engagement & kepuasan user dengan sistem request otomatis.
        </p>
        
        <!-- Stats Grid -->
        <div class="grid grid-cols-3 gap-4 mt-6">
            <div class="glass-panel rounded-2xl p-4 border border-white/5 hover:border-emerald-500/20 transition-all duration-300">
                <div class="flex items-center gap-2 mb-2">
                    <TrendingUp class="w-4 h-4 text-emerald-400" />
                    <div class="text-[10px] text-slate-500 font-bold uppercase tracking-wider">Satisfaction</div>
                </div>
                <div class="text-2xl font-bold text-white">+45%</div>
            </div>
            <div class="glass-panel rounded-2xl p-4 border border-white/5 hover:border-emerald-500/20 transition-all duration-300">
                <div class="flex items-center gap-2 mb-2">
                    <Sparkles class="w-4 h-4 text-emerald-400" />
                    <div class="text-[10px] text-slate-500 font-bold uppercase tracking-wider">Retention</div>
                </div>
                <div class="text-2xl font-bold text-white">2.3x</div>
            </div>
            <div class="glass-panel rounded-2xl p-4 border border-white/5 hover:border-emerald-500/20 transition-all duration-300">
                <div class="flex items-center gap-2 mb-2">
                    <Clock class="w-4 h-4 text-emerald-400" />
                    <div class="text-[10px] text-slate-500 font-bold uppercase tracking-wider">Response</div>
                </div>
                <div class="text-2xl font-bold text-white">&lt;2h</div>
            </div>
        </div>
    </div>

    <!-- Request Flow Visual -->
    <div class="flex-1 relative min-h-[500px]">
        <!-- Background Gradient -->
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_top_right,rgba(16,185,129,0.08),transparent_60%)] rounded-3xl"></div>
        
        <!-- Flow Container -->
        <div class="relative h-full flex flex-col justify-center gap-6 p-8">
            
            <!-- Step 1: User Request -->
            <div class="relative group" style="perspective: 1200px;">
                <div class="rounded-2xl p-6 border transition-all duration-500 {step1Hovered ? 'border-emerald-500/40 shadow-[0_20px_50px_rgba(16,185,129,0.2)]' : 'border-emerald-500/20'}"
                     style:transform-style="preserve-3d"
                     style:transform={step1Hovered ? 'perspective(1000px) rotateY(0deg) rotateX(0deg)' : 'perspective(1000px) rotateY(-4deg) rotateX(3deg)'}
                     on:mouseenter={() => step1Hovered = true}
                     on:mouseleave={() => step1Hovered = false}
                     role="presentation">
                    
                    <!-- Glass panel base -->
                    <div class="absolute inset-0 glass-panel rounded-2xl"></div>
                    
                    <!-- Glass Reflection Overlay -->
                    <div class="absolute inset-0 rounded-2xl bg-gradient-to-tr from-white/15 via-white/5 to-transparent pointer-events-none transition-opacity duration-500"
                         class:opacity-60={!step1Hovered}
                         class:opacity-80={step1Hovered}
                         style:transform="translateZ(5px)"></div>
                    
                    <div class="relative" style:transform="translateZ(20px)">
                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-xl bg-emerald-500/20 flex items-center justify-center border border-emerald-500/30 group-hover:bg-emerald-500/30 transition-all duration-300"
                                 style:transform="translateZ(30px)">
                                <MessageSquarePlus class="w-6 h-6 text-emerald-400" />
                            </div>
                            <div class="flex-1">
                                <div class="text-[10px] text-emerald-400 font-bold uppercase tracking-widest mb-2">Step 1</div>
                                <div class="text-white font-bold mb-2">User Requests Film</div>
                                <div class="text-sm text-slate-400 leading-relaxed">User bisa request film yang diinginkan melalui bot atau mini app</div>
                            </div>
                        </div>
                        
                        <!-- Mock Request Form -->
                        <div class="mt-4 pt-4 border-t border-white/5"
                             style:transform="translateZ(25px)">
                            <div class="space-y-2">
                                <div class="flex items-center gap-2 text-xs">
                                    <div class="w-2 h-2 rounded-full bg-emerald-400/50"></div>
                                    <span class="text-slate-500">Film:</span>
                                    <span class="text-white font-medium">Drama Korea Terbaru</span>
                                </div>
                                <div class="flex items-center gap-2 text-xs">
                                    <div class="w-2 h-2 rounded-full bg-emerald-400/30"></div>
                                    <span class="text-slate-500">Source:</span>
                                    <span class="text-slate-400">Netflix</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Connection Line -->
                <div class="absolute left-1/2 -bottom-4 w-0.5 h-8 bg-gradient-to-b from-emerald-500/50 to-emerald-500/20 z-0 hidden md:block"></div>
                <div class="absolute left-1/2 -bottom-2 -translate-x-1/2">
                    <ArrowRight class="w-4 h-4 text-emerald-500/50 rotate-90 hidden md:block" />
                </div>
            </div>

            <!-- Step 2: Admin Processing -->
            <div class="relative group mt-4" style="perspective: 1200px;">
                <div class="rounded-2xl p-6 border transition-all duration-500 {step2Hovered ? 'border-emerald-500/30 shadow-[0_20px_50px_rgba(16,185,129,0.15)]' : 'border-white/5'}"
                     style:transform-style="preserve-3d"
                     style:transform={step2Hovered ? 'perspective(1000px) rotateY(0deg) rotateX(0deg)' : 'perspective(1000px) rotateY(4deg) rotateX(3deg)'}
                     on:mouseenter={() => step2Hovered = true}
                     on:mouseleave={() => step2Hovered = false}
                     role="presentation">
                    
                    <!-- Glass panel base -->
                    <div class="absolute inset-0 glass-panel rounded-2xl"></div>
                    
                    <!-- Glass Reflection Overlay -->
                    <div class="absolute inset-0 rounded-2xl bg-gradient-to-bl from-white/15 via-white/5 to-transparent pointer-events-none transition-opacity duration-500"
                         class:opacity-50={!step2Hovered}
                         class:opacity-75={step2Hovered}
                         style:transform="translateZ(5px)"></div>
                    
                    <div class="relative" style:transform="translateZ(20px)">
                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-xl bg-blue-500/20 flex items-center justify-center border border-blue-500/30 group-hover:bg-blue-500/30 transition-all duration-300"
                                 style:transform="translateZ(30px)">
                                <CheckCircle2 class="w-6 h-6 text-blue-400" />
                            </div>
                            <div class="flex-1">
                                <div class="text-[10px] text-blue-400 font-bold uppercase tracking-widest mb-2">Step 2</div>
                                <div class="text-white font-bold mb-2">Admin Receives & Processes</div>
                                <div class="text-sm text-slate-400 leading-relaxed">Request masuk ke admin panel Anda untuk diproses</div>
                            </div>
                        </div>
                        
                        <!-- Admin Queue Preview -->
                        <div class="mt-4 pt-4 border-t border-white/5"
                             style:transform="translateZ(25px)">
                            <div class="space-y-2">
                                <div class="flex items-center justify-between text-xs">
                                    <div class="flex items-center gap-2">
                                        <div class="w-2 h-2 rounded-full bg-yellow-400 animate-pulse"></div>
                                        <span class="text-slate-400">Status:</span>
                                        <span class="text-yellow-400 font-semibold uppercase text-[10px] tracking-wider">Processing</span>
                                    </div>
                                    <span class="text-slate-500">2h ago</span>
                                </div>
                                <div class="flex items-center justify-between text-xs">
                                    <div class="flex items-center gap-2">
                                        <div class="w-2 h-2 rounded-full bg-emerald-400"></div>
                                        <span class="text-slate-400">Priority:</span>
                                        <span class="text-emerald-400 font-medium">High</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Connection Line -->
                <div class="absolute left-1/2 -bottom-4 w-0.5 h-8 bg-gradient-to-b from-blue-500/50 to-purple-500/20 z-0 hidden md:block"></div>
                <div class="absolute left-1/2 -bottom-2 -translate-x-1/2">
                    <ArrowRight class="w-4 h-4 text-blue-500/50 rotate-90 hidden md:block" />
                </div>
            </div>

            <!-- Step 3: User Notification -->
            <div class="relative group mt-4" style="perspective: 1200px;">
                <div class="rounded-2xl p-6 border transition-all duration-500 {step3Hovered ? 'border-purple-500/30 shadow-[0_20px_50px_rgba(168,85,247,0.15)]' : 'border-white/5'}"
                     style:transform-style="preserve-3d"
                     style:transform={step3Hovered ? 'perspective(1000px) rotateY(0deg) rotateX(0deg)' : 'perspective(1000px) rotateY(-4deg) rotateX(3deg)'}
                     on:mouseenter={() => step3Hovered = true}
                     on:mouseleave={() => step3Hovered = false}
                     role="presentation">
                    
                    <!-- Glass panel base -->
                    <div class="absolute inset-0 glass-panel rounded-2xl"></div>
                    
                    <!-- Glass Reflection Overlay -->
                    <div class="absolute inset-0 rounded-2xl bg-gradient-to-tr from-white/15 via-white/5 to-transparent pointer-events-none transition-opacity duration-500"
                         class:opacity-50={!step3Hovered}
                         class:opacity-75={step3Hovered}
                         style:transform="translateZ(5px)"></div>
                    
                    <div class="relative" style:transform="translateZ(20px)">
                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-xl bg-purple-500/20 flex items-center justify-center border border-purple-500/30 group-hover:bg-purple-500/30 transition-all duration-300 relative"
                                 style:transform="translateZ(30px)">
                                <Bell class="w-6 h-6 text-purple-400" />
                                <div class="absolute -top-1 -right-1 w-3 h-3 bg-purple-500 rounded-full animate-ping"></div>
                                <div class="absolute -top-1 -right-1 w-3 h-3 bg-purple-500 rounded-full"></div>
                            </div>
                            <div class="flex-1">
                                <div class="text-[10px] text-purple-400 font-bold uppercase tracking-widest mb-2">Step 3</div>
                                <div class="text-white font-bold mb-2">User Gets Notified</div>
                                <div class="text-sm text-slate-400 leading-relaxed">Notifikasi otomatis saat request selesai diproses</div>
                            </div>
                        </div>
                        
                        <!-- Success Message -->
                        <div class="mt-4 pt-4 border-t border-white/5"
                             style:transform="translateZ(25px)">
                            <div class="flex items-start gap-3 bg-emerald-500/10 border border-emerald-500/20 rounded-xl p-3">
                                <CheckCircle2 class="w-4 h-4 text-emerald-400 flex-shrink-0 mt-0.5" />
                                <div class="text-xs text-emerald-300 leading-relaxed">
                                    Film Anda sudah tersedia! Cek sekarang di /start DK001
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
        </div>

        <!-- Decorative Elements -->
        <div class="absolute top-0 right-0 w-32 h-32 bg-emerald-500/10 rounded-full blur-3xl opacity-50 animate-pulse" style="animation-duration: 4s;"></div>
        <div class="absolute bottom-0 left-0 w-24 h-24 bg-purple-500/10 rounded-full blur-2xl opacity-40 animate-pulse" style="animation-duration: 6s; animation-delay: 1s;"></div>
    </div>
</div>
