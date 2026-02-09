<script>
    import { Lock, Users, Play, Radio, MessageCircle, Shield, Eye, Wifi, Clock, BarChart } from 'lucide-svelte';

    export let mode = 'privacy';
    export let switchMode;
    
    let groupMockupHovered = false;
    let privacyMockupHovered = false;
    
    const floatingComments = [
        { text: "Seru banget!", delay: 0, x: 10, y: 20 },
        { text: "Nonton bareng kuy", delay: 0.8, x: 60, y: 15 },
        { text: "🔥🔥🔥", delay: 1.6, x: 35, y: 35 },
        { text: "Gaskeun!", delay: 2.4, x: 75, y: 30 }
    ];
</script>

<!-- Feature 2: Strategy -->
<div class="flex flex-col md:flex-row-reverse items-center gap-16 reveal">
    <div class="flex-1 space-y-8">
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-blue-500/30 bg-blue-500/10 text-blue-400 text-[10px] font-bold tracking-widest uppercase">
            Engagement Control
        </div>
        <h2 class="text-4xl md:text-6xl font-bold leading-tight text-white relative inline-block">
            Privasi atau <br>
            <span class="bg-gradient-to-r from-blue-400 via-cyan-300 to-blue-500 bg-clip-text text-transparent">Viralitas</span>?
            <svg class="absolute -bottom-3 -right-16 w-24 h-12 text-blue-400/40 hidden md:block animate-pulse" viewBox="0 0 100 50" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round">
                <path d="M5 25 Q25 15, 45 25 T85 25" class="animate-[dash_2s_ease-in-out_infinite]" stroke-dasharray="3 6"/>
                <text x="85" y="20" class="text-xs font-handwriting fill-current" style="font-family: 'Comic Sans MS', cursive; font-size: 10px;">You choose!</text>
            </svg>
        </h2>
        <p class="text-slate-400 text-lg leading-relaxed">
            Kendalikan cara audiens menikmati konten. Mode <strong>Privacy</strong> untuk eksklusivitas atau <strong>Watch Together</strong> untuk viralitas grup.
        </p>
        <div class="grid grid-cols-2 gap-4 mt-6">
            <button 
                on:click={() => switchMode('privacy')}
                class="glass-panel p-6 rounded-3xl text-center border transition-all duration-500 cursor-pointer hover:scale-[1.02] active:scale-[0.98]
                    {mode === 'privacy' ? 'bg-blue-500/10 border-blue-500/30 shadow-[0_10px_30px_rgba(59,130,246,0.2)]' : 'border-white/5 hover:border-white/10'}"
                style="transition-delay: {mode === 'privacy' ? '0ms' : '100ms'}"
            >
                <Lock class="w-8 h-8 mb-4 mx-auto transition-all duration-500 {mode === 'privacy' ? 'text-blue-400 scale-110' : 'text-slate-400'}" />
                <div class="text-sm font-bold transition-colors duration-500 {mode === 'privacy' ? 'text-blue-300' : 'text-white'}">Privacy Mode</div>
            </button>
            <button 
                on:click={() => switchMode('group')}
                class="glass-panel p-6 rounded-3xl text-center border transition-all duration-500 cursor-pointer hover:scale-[1.02] active:scale-[0.98]
                    {mode === 'group' ? 'bg-blue-500/10 border-blue-500/30 shadow-[0_10px_30px_rgba(59,130,246,0.2)]' : 'border-white/5 hover:border-white/10'}"
                style="transition-delay: {mode === 'group' ? '0ms' : '100ms'}"
            >
                <Users class="w-8 h-8 mb-4 mx-auto transition-all duration-500 {mode === 'group' ? 'text-blue-400 scale-110' : 'text-slate-400'}" />
                <div class="text-sm font-bold transition-colors duration-500 {mode === 'group' ? 'text-blue-300' : 'text-white'}">Group Watch</div>
            </button>
        </div>
    </div>
    <div class="flex-1 w-full relative">
        <!-- Background Glow (Privacy Mode) -->
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_bottom_right,rgba(59,130,246,0.12),transparent_70%)] rounded-3xl transition-opacity duration-700 {mode === 'privacy' ? 'opacity-100' : 'opacity-0'}"></div>
        
        <!-- Background Glow (Group Watch Mode) -->
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_top_left,rgba(59,130,246,0.12),transparent_70%)] rounded-3xl transition-opacity duration-700 {mode === 'group' ? 'opacity-100' : 'opacity-0'}"></div>
        
        <!-- Group Watch Feature -->
        <div class="w-3/4 absolute top-0 left-0 transition-all duration-500"
            style="perspective: 1200px;"
            class:z-20={mode === 'group'}
            class:z-10={mode !== 'group'}
            class:opacity-100={mode === 'group'}
            class:opacity-40={mode !== 'group'}
            class:blur-0={mode === 'group'}
            class:blur-sm={mode !== 'group'}
            class:scale-100={mode === 'group'}
            class:scale-95={mode !== 'group'}>
            <div class="glass-panel rounded-[2.5rem] p-4 border transition-all duration-500 {mode === 'group' ? 'border-blue-500/30 shadow-[0_20px_50px_rgba(59,130,246,0.15)]' : 'border-white/5'}"
                 style:transform-style="preserve-3d"
                 style:transform={groupMockupHovered ? 'perspective(1000px) rotateY(0deg) rotateX(0deg)' : 'perspective(1000px) rotateY(-6deg) rotateX(4deg) rotate(-3deg)'}
                 on:mouseenter={() => groupMockupHovered = true}
                 on:mouseleave={() => groupMockupHovered = false}
                 role="presentation">
                
                <!-- Glass Reflection Overlay -->
                <div class="absolute inset-0 rounded-[2.5rem] bg-gradient-to-tr from-white/15 via-white/5 to-transparent pointer-events-none transition-opacity duration-500"
                     class:opacity-70={groupMockupHovered}
                     class:opacity-40={!groupMockupHovered}
                     style:transform="translateZ(5px)"></div>
                
                <div class="aspect-video bg-gradient-to-br from-blue-950/80 via-blue-900/60 to-purple-950/50 rounded-2xl flex items-center justify-center relative overflow-hidden group"
                     style:transform="translateZ(20px)">
                    <!-- Gradient mesh background for depth -->
                    <div class="absolute inset-0 bg-[radial-gradient(circle_at_30%_40%,rgba(59,130,246,0.15),transparent_50%),radial-gradient(circle_at_70%_60%,rgba(168,85,247,0.1),transparent_50%)]"></div>
                    
                    <!-- Simulated video content with gradient -->
                    <div class="absolute inset-0 bg-gradient-to-br from-blue-500/20 to-purple-500/10 opacity-0 group-hover:opacity-100 transition-opacity"></div>
                    
                    <!-- Play button with glow -->
                    <div style:transform="translateZ(30px)" class="relative z-10 flex items-center justify-center">
                        <div class="w-16 h-16 rounded-full bg-white/90 backdrop-blur-md flex items-center justify-center shadow-[0_0_30px_rgba(59,130,246,0.6)] hover:scale-110 transition-transform cursor-pointer">
                            <Play class="w-7 h-7 fill-blue-600 text-blue-600 ml-0.5" />
                        </div>
                    </div>
                    
                    <!-- Live indicator -->
                    <div class="absolute top-4 left-4 flex items-center gap-2 bg-red-500/90 backdrop-blur-sm px-3 py-1.5 rounded-full shadow-lg"
                         style:transform="translateZ(35px)">
                        <Radio class="w-3 h-3 text-white animate-pulse" />
                        <span class="text-white text-[10px] font-bold uppercase tracking-wider">LIVE</span>
                    </div>
                    
                    <!-- Viewer count with animation -->
                    <div class="absolute top-4 right-4 flex items-center gap-2 bg-white/95 backdrop-blur-md px-3 py-1.5 rounded-full shadow-lg border border-blue-200/50"
                         style:transform="translateZ(35px)">
                        <Eye class="w-3 h-3 text-blue-600" />
                        <span class="text-blue-600 text-[10px] font-bold tabular-nums">128</span>
                        <BarChart class="w-3 h-3 text-green-500" />
                    </div>
                    
                    {#if mode === 'group'}
                        <!-- Floating reactions and comments -->
                        {#each floatingComments as comment}
                            <div 
                                class="absolute bg-white/95 backdrop-blur-sm text-slate-900 text-xs font-bold px-3 py-1.5 rounded-full shadow-lg animate-[float_3s_ease-in-out_infinite] opacity-0 border border-blue-100"
                                style="left: {comment.x}%; top: {comment.y}%; animation-delay: {comment.delay}s; animation-fill-mode: forwards; transform: translateZ(40px);"
                            >
                                {comment.text}
                            </div>
                        {/each}
                    {/if}
                    
                    <!-- Video progress bar -->
                    <div class="absolute bottom-16 left-4 right-4"
                         style:transform="translateZ(30px)">
                        <div class="h-1 bg-white/20 rounded-full overflow-hidden backdrop-blur-sm">
                            <div class="h-full w-[45%] bg-gradient-to-r from-blue-400 to-cyan-400 rounded-full shadow-[0_0_10px_rgba(59,130,246,0.8)]"></div>
                        </div>
                        <div class="flex justify-between mt-1 px-1">
                            <span class="text-[9px] text-white/70 font-mono">12:34</span>
                            <span class="text-[9px] text-white/70 font-mono">28:00</span>
                        </div>
                    </div>
                    
                    <!-- Participant avatars and chat preview -->
                    <div class="absolute bottom-4 left-4 right-4 flex gap-3 items-end"
                         style:transform="translateZ(35px)">
                        <!-- Chat messages preview -->
                        <div class="flex-1 space-y-1.5 max-w-[60%]">
                            <div class="bg-black/60 backdrop-blur-md text-white text-[9px] px-2 py-1 rounded-lg leading-tight shadow-lg">
                                <span class="text-blue-300 font-bold">@Alex:</span> ini bagus banget!
                            </div>
                            <div class="bg-black/60 backdrop-blur-md text-white text-[9px] px-2 py-1 rounded-lg leading-tight shadow-lg">
                                <span class="text-purple-300 font-bold">@Sarah:</span> lanjut episode 2 yuk
                            </div>
                        </div>
                        
                        <!-- Active viewers with avatars -->
                        <div class="flex items-center gap-2 bg-gradient-to-r from-blue-500/90 to-purple-500/90 backdrop-blur-md px-3 py-1.5 rounded-full shadow-lg border border-white/20">
                            <Users class="w-3 h-3 text-white" />
                            <div class="flex -space-x-1.5">
                                <div class="w-5 h-5 rounded-full bg-gradient-to-br from-blue-400 to-blue-600 border-2 border-white shadow-md"></div>
                                <div class="w-5 h-5 rounded-full bg-gradient-to-br from-purple-400 to-purple-600 border-2 border-white shadow-md"></div>
                                <div class="w-5 h-5 rounded-full bg-gradient-to-br from-pink-400 to-pink-600 border-2 border-white shadow-md"></div>
                                <div class="w-5 h-5 rounded-full bg-gradient-to-br from-cyan-400 to-cyan-600 border-2 border-white shadow-md flex items-center justify-center">
                                    <span class="text-[7px] text-white font-bold">+124</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Privacy Mode Feature -->
        <div class="w-3/4 ml-auto mt-24 transition-all duration-500"
            style="perspective: 1200px;"
            class:z-20={mode === 'privacy'}
            class:z-10={mode !== 'privacy'}
            class:opacity-100={mode === 'privacy'}
            class:opacity-40={mode !== 'privacy'}
            class:blur-0={mode === 'privacy'}
            class:blur-sm={mode !== 'privacy'}
            class:scale-100={mode === 'privacy'}
            class:scale-95={mode !== 'privacy'}>
            <div class="glass-panel rounded-[2.5rem] p-4 border transition-all duration-500 {mode === 'privacy' ? 'border-blue-500/30 shadow-[0_20px_50px_rgba(59,130,246,0.15)]' : 'border-white/5'}"
                 style:transform-style="preserve-3d"
                 style:transform={privacyMockupHovered ? 'perspective(1000px) rotateY(0deg) rotateX(0deg)' : 'perspective(1000px) rotateY(6deg) rotateX(4deg) rotate(3deg)'}
                 on:mouseenter={() => privacyMockupHovered = true}
                 on:mouseleave={() => privacyMockupHovered = false}
                 role="presentation">
                
                <!-- Glass Reflection Overlay -->
                <div class="absolute inset-0 rounded-[2.5rem] bg-gradient-to-bl from-white/15 via-white/5 to-transparent pointer-events-none transition-opacity duration-500"
                     class:opacity-70={privacyMockupHovered}
                     class:opacity-40={!privacyMockupHovered}
                     style:transform="translateZ(5px)"></div>
                
                <div class="aspect-video bg-gradient-to-br from-slate-950/90 via-slate-900/80 to-blue-950/70 rounded-2xl flex items-center justify-center relative overflow-hidden"
                     style:transform="translateZ(20px)">
                    <!-- Secure gradient mesh -->
                    <div class="absolute inset-0 bg-[radial-gradient(circle_at_50%_50%,rgba(59,130,246,0.08),transparent_60%)]"></div>
                    
                    <!-- Encryption pattern overlay -->
                    <div class="absolute inset-0 opacity-[0.03]" style="background-image: repeating-linear-gradient(45deg, transparent, transparent 10px, rgba(59,130,246,0.3) 10px, rgba(59,130,246,0.3) 11px);"></div>
                    
                    <!-- Lock icon with secure glow -->
                    <div style:transform="translateZ(30px)" class="flex items-center justify-center relative">
                        <div class="absolute inset-0 blur-2xl bg-blue-500/30 rounded-full scale-150 animate-[lockPulse_2s_ease-in-out_infinite]"></div>
                        <div class="relative w-14 h-14 rounded-2xl bg-gradient-to-br from-blue-500/20 to-blue-600/10 backdrop-blur-md flex items-center justify-center border border-blue-400/30 shadow-[0_0_30px_rgba(59,130,246,0.4)]">
                            <Lock class="w-7 h-7 transition-all duration-500 {mode === 'privacy' ? 'text-blue-400' : 'text-white/30'}" />
                        </div>
                    </div>
                    
                    {#if mode === 'privacy'}
                        <!-- Animated secure ring -->
                        <div class="absolute inset-0 border-4 border-blue-500/20 rounded-2xl animate-[secureRing_3s_ease-in-out_infinite]"
                             style:transform="translateZ(15px)"></div>
                        
                        <!-- Security badges cluster -->
                        <div class="absolute top-3 right-3 flex flex-col gap-2"
                             style:transform="translateZ(30px)">
                            <!-- Secured badge -->
                            <div class="flex items-center gap-1.5 px-2.5 py-1 rounded-lg bg-gradient-to-r from-blue-500/20 to-blue-600/20 backdrop-blur-md border border-blue-400/40 shadow-lg">
                                <div class="w-1.5 h-1.5 rounded-full bg-blue-400 animate-pulse shadow-[0_0_6px_rgba(59,130,246,0.8)]"></div>
                                <span class="text-[9px] text-blue-300 font-bold uppercase tracking-wider">Secured</span>
                            </div>
                            <!-- Encryption badge -->
                            <div class="flex items-center gap-1.5 px-2.5 py-1 rounded-lg bg-gradient-to-r from-green-500/15 to-emerald-600/15 backdrop-blur-md border border-green-400/30 shadow-lg">
                                <Shield class="w-2.5 h-2.5 text-green-400" />
                                <span class="text-[8px] text-green-300 font-bold uppercase tracking-wider">AES-256</span>
                            </div>
                        </div>
                        
                        <!-- Private session info -->
                        <div class="absolute top-3 left-3 flex items-center gap-2 px-2.5 py-1 rounded-lg bg-black/40 backdrop-blur-md border border-white/10 shadow-lg"
                             style:transform="translateZ(30px)">
                            <Eye class="w-3 h-3 text-white/70" />
                            <span class="text-[9px] text-white/70 font-mono uppercase tracking-wide">Private</span>
                        </div>
                        
                        <!-- DRM watermark (semi-transparent) -->
                        <div class="absolute inset-0 flex items-center justify-center pointer-events-none"
                             style:transform="translateZ(25px)">
                            <div class="text-white/[0.08] text-xs font-bold uppercase tracking-[0.3em] rotate-[-25deg] select-none">
                                DRM Protected • Single Viewer
                            </div>
                        </div>
                        
                        <!-- Secure connection indicator -->
                        <div class="absolute bottom-3 left-3 flex items-center gap-2 px-2.5 py-1 rounded-lg bg-gradient-to-r from-blue-500/15 to-purple-500/15 backdrop-blur-md border border-blue-300/20 shadow-lg"
                             style:transform="translateZ(30px)">
                            <Wifi class="w-3 h-3 text-blue-400" />
                            <span class="text-[8px] text-blue-300 font-mono uppercase tracking-wide">TLS 1.3</span>
                            <div class="w-px h-3 bg-white/20"></div>
                            <Clock class="w-2.5 h-2.5 text-purple-400" />
                            <span class="text-[8px] text-purple-300 font-mono tabular-nums">24h</span>
                        </div>
                        
                        <!-- Exclusive access badge -->
                        <div class="absolute bottom-3 right-3 flex items-center gap-1.5 px-2.5 py-1 rounded-lg bg-gradient-to-r from-amber-500/20 to-yellow-600/20 backdrop-blur-md border border-amber-400/40 shadow-lg"
                             style:transform="translateZ(30px)">
                            <div class="w-2 h-2 rounded-sm bg-gradient-to-br from-amber-400 to-yellow-500 shadow-[0_0_8px_rgba(251,191,36,0.6)]"></div>
                            <span class="text-[8px] text-amber-300 font-bold uppercase tracking-wider">Premium</span>
                        </div>
                    {/if}
                </div>
            </div>
        </div>
    </div>
</div>

<style>
    @keyframes float {
        0% { 
            opacity: 0; 
            transform: translateY(10px) scale(0.8); 
        }
        10% { 
            opacity: 1; 
            transform: translateY(0) scale(1); 
        }
        90% { 
            opacity: 1; 
            transform: translateY(-5px) scale(1); 
        }
        100% { 
            opacity: 0; 
            transform: translateY(-15px) scale(0.9); 
        }
    }
    
    @keyframes lockPulse {
        0%, 100% { 
            transform: scale(1); 
            filter: drop-shadow(0 0 0 rgba(59, 130, 246, 0)); 
        }
        50% { 
            transform: scale(1.05); 
            filter: drop-shadow(0 0 15px rgba(59, 130, 246, 0.6)); 
        }
    }
    
    @keyframes secureRing {
        0% { 
            transform: scale(1); 
            opacity: 0.3; 
        }
        50% { 
            transform: scale(1.02); 
            opacity: 0.6; 
        }
        100% { 
            transform: scale(1); 
            opacity: 0.3; 
        }
    }
    
    @keyframes dash {
        0%, 100% { stroke-dashoffset: 0; }
        50% { stroke-dashoffset: 15; }
    }
</style>