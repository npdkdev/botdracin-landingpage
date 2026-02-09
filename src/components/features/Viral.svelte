<script>
    import { Crown, User, DollarSign } from 'lucide-svelte';
</script>

<div class="text-center max-w-4xl mx-auto pt-0 md:pt-10 reveal">
    <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-purple-500/30 bg-purple-500/10 text-purple-400 text-[10px] font-bold tracking-widest uppercase mb-8">
        Organic Growth
    </div>
    <h2 class="text-4xl md:text-7xl font-bold mb-8 gradient-text">User = Marketing.</h2>
    <p class="text-slate-400 text-xl max-w-2xl mx-auto mb-20">
        Sistem komisi bertingkat membuat user berlomba-lomba mengajak teman. <br>Tanpa biaya iklan.
    </p>
    
    <div class="relative h-[550px] glass-panel rounded-[3rem] w-full overflow-hidden flex items-center justify-center border border-purple-500/20 shadow-[0_0_120px_rgba(168,85,247,0.25)]">
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_center,rgba(168,85,247,0.25),rgba(236,72,153,0.15)_50%,transparent_80%)]"></div>
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_60%_40%,rgba(236,72,153,0.15),transparent_50%)]"></div>
        
        <!-- Network Visualization -->
        <div class="relative w-full h-full flex items-center justify-center">
            
            <!-- Orbits (Static Visuals for structure) -->
            <div class="absolute w-[350px] h-[350px] rounded-full border border-purple-500/10 border-dashed opacity-50 animate-[spin_60s_linear_infinite]"></div>
            <div class="absolute w-[500px] h-[500px] rounded-full border border-purple-500/5 opacity-30"></div>

            <!-- Center Node -->
            <div class="absolute z-30 flex flex-col items-center">
                <div class="w-24 h-24 rounded-full glass-panel bg-gradient-to-br from-white/10 to-purple-500/10 border border-purple-500/50 flex items-center justify-center shadow-[0_0_100px_rgba(168,85,247,0.6),0_0_60px_rgba(236,72,153,0.4)] relative">
                    <div class="absolute inset-0 rounded-full border-2 border-purple-400/40 animate-[ping_2s_ease-in-out_infinite] opacity-30"></div>
                    <div class="absolute inset-0 rounded-full border-2 border-fuchsia-400/30 animate-[ping_2s_ease-in-out_0.5s_infinite] opacity-20"></div>
                    <div class="relative">
                        <Crown class="w-10 h-10 text-purple-300 fill-purple-300/30 drop-shadow-[0_0_12px_rgba(168,85,247,0.8)] animate-[pulse_3s_ease-in-out_infinite]" />
                        <div class="absolute -top-1 -right-1 w-3 h-3 bg-yellow-400 rounded-full blur-[2px] animate-[pulse_2s_ease-in-out_infinite]"></div>
                    </div>
                </div>
                <div class="mt-4 glass-panel px-4 py-1.5 rounded-full text-[10px] font-bold text-white tracking-widest uppercase shadow-lg border border-purple-500/20">YOU</div>
            </div>

            <!-- Spinning Layer 1 (Inner Network - 3 Nodes) -->
            <div class="absolute inset-0 animate-[spin_40s_linear_infinite]">
                <svg class="absolute inset-0 w-full h-full pointer-events-none stroke-purple-500/30" stroke-width="1.5">
                    <line x1="50%" y1="50%" x2="50%" y2="30%" />
                    <line x1="50%" y1="50%" x2="33%" y2="60%" />
                    <line x1="50%" y1="50%" x2="67%" y2="60%" />
                    <line x1="50%" y1="30%" x2="33%" y2="60%" stroke-opacity="0.3" stroke-width="0.5" />
                    <line x1="33%" y1="60%" x2="67%" y2="60%" stroke-opacity="0.3" stroke-width="0.5" />
                    <line x1="67%" y1="60%" x2="50%" y2="30%" stroke-opacity="0.3" stroke-width="0.5" />
                </svg>
                
                <div class="absolute top-[30%] left-[50%] -translate-x-1/2 -translate-y-1/2 w-14 h-14 rounded-full glass-panel bg-black/40 flex items-center justify-center border border-white/20 shadow-[0_0_20px_rgba(168,85,247,0.2)] z-10">
                    <User class="w-5 h-5 text-purple-200" />
                </div>
                <div class="absolute top-[60%] left-[33%] -translate-x-1/2 -translate-y-1/2 w-14 h-14 rounded-full glass-panel bg-black/40 flex items-center justify-center border border-white/20 shadow-[0_0_20px_rgba(168,85,247,0.2)] z-10">
                    <User class="w-5 h-5 text-purple-200" />
                </div>
                <div class="absolute top-[60%] left-[67%] -translate-x-1/2 -translate-y-1/2 w-14 h-14 rounded-full glass-panel bg-black/40 flex items-center justify-center border border-white/20 shadow-[0_0_20px_rgba(168,85,247,0.2)] z-10">
                    <User class="w-5 h-5 text-purple-200" />
                </div>
            </div>

            <!-- Spinning Layer 2 (Outer Network - 5 Nodes - Reverse) -->
            <div class="absolute inset-0 animate-[spin_60s_linear_infinite_reverse]">
                 <svg class="absolute inset-0 w-full h-full pointer-events-none stroke-purple-500/10" stroke-width="1">
                    <line x1="50%" y1="50%" x2="50%" y2="10%" />
                    <line x1="50%" y1="50%" x2="85%" y2="35%" />
                    <line x1="50%" y1="50%" x2="75%" y2="85%" />
                    <line x1="50%" y1="50%" x2="25%" y2="85%" />
                    <line x1="50%" y1="50%" x2="15%" y2="35%" />
                </svg>

                <div class="absolute top-[10%] left-[50%] -translate-x-1/2 -translate-y-1/2 w-10 h-10 rounded-full glass-panel bg-white/5 border border-white/10 flex items-center justify-center z-10">
                    <User class="w-3 h-3 text-white/40" />
                </div>
                <div class="absolute top-[35%] left-[85%] -translate-x-1/2 -translate-y-1/2 w-10 h-10 rounded-full glass-panel bg-white/5 border border-white/10 flex items-center justify-center z-10">
                    <User class="w-3 h-3 text-white/40" />
                </div>
                <div class="absolute top-[85%] left-[75%] -translate-x-1/2 -translate-y-1/2 w-10 h-10 rounded-full glass-panel bg-white/5 border border-white/10 flex items-center justify-center z-10">
                    <User class="w-3 h-3 text-white/40" />
                </div>
                <div class="absolute top-[85%] left-[25%] -translate-x-1/2 -translate-y-1/2 w-10 h-10 rounded-full glass-panel bg-white/5 border border-white/10 flex items-center justify-center z-10">
                    <User class="w-3 h-3 text-white/40" />
                </div>
                <div class="absolute top-[35%] left-[15%] -translate-x-1/2 -translate-y-1/2 w-10 h-10 rounded-full glass-panel bg-white/5 border border-white/10 flex items-center justify-center z-10">
                    <User class="w-3 h-3 text-white/40" />
                </div>
            </div>

            <!-- Money Flow Particles -->
            <!-- From top outer node -->
            <div class="money-particle" style="--start-x: 50%; --start-y: 10%; --delay: 0s;"></div>
            <div class="money-particle" style="--start-x: 50%; --start-y: 10%; --delay: 2s;"></div>
            <div class="money-particle" style="--start-x: 50%; --start-y: 10%; --delay: 4s;"></div>
            
            <!-- From right outer nodes -->
            <div class="money-particle" style="--start-x: 85%; --start-y: 35%; --delay: 0.5s;"></div>
            <div class="money-particle" style="--start-x: 85%; --start-y: 35%; --delay: 2.5s;"></div>
            <div class="money-particle" style="--start-x: 75%; --start-y: 85%; --delay: 1s;"></div>
            <div class="money-particle" style="--start-x: 75%; --start-y: 85%; --delay: 3s;"></div>
            
            <!-- From left outer nodes -->
            <div class="money-particle" style="--start-x: 15%; --start-y: 35%; --delay: 1.5s;"></div>
            <div class="money-particle" style="--start-x: 15%; --start-y: 35%; --delay: 3.5s;"></div>
            <div class="money-particle" style="--start-x: 25%; --start-y: 85%; --delay: 0.8s;"></div>
            <div class="money-particle" style="--start-x: 25%; --start-y: 85%; --delay: 2.8s;"></div>

            <!-- Live Activity Cards -->
            <div class="activity-card" style="top: 15%; left: 75%; --delay: 0s;">
                <div class="flex items-center gap-2">
                    <div class="w-6 h-6 rounded-full bg-gradient-to-br from-green-400 to-emerald-500 flex items-center justify-center">
                        <DollarSign class="w-3 h-3 text-white" />
                    </div>
                    <div>
                        <div class="text-[10px] font-bold text-white">New Referral</div>
                        <div class="text-[9px] text-green-400">+Rp 25.000</div>
                    </div>
                </div>
            </div>

            <div class="activity-card" style="top: 70%; left: 15%; --delay: 2s;">
                <div class="flex items-center gap-2">
                    <div class="w-6 h-6 rounded-full bg-gradient-to-br from-purple-400 to-fuchsia-500 flex items-center justify-center">
                        <User class="w-3 h-3 text-white" />
                    </div>
                    <div>
                        <div class="text-[10px] font-bold text-white">Budi joined</div>
                        <div class="text-[9px] text-purple-300">via Siti</div>
                    </div>
                </div>
            </div>

            <div class="activity-card" style="top: 25%; left: 10%; --delay: 4s;">
                <div class="flex items-center gap-2">
                    <div class="w-6 h-6 rounded-full bg-gradient-to-br from-blue-400 to-cyan-500 flex items-center justify-center">
                        <Crown class="w-3 h-3 text-white" />
                    </div>
                    <div>
                        <div class="text-[10px] font-bold text-white">Level 2 Commission</div>
                        <div class="text-[9px] text-cyan-300">+Rp 15.000</div>
                    </div>
                </div>
            </div>

        </div>
    </div>
</div>

<style>
    .gradient-text {
        background: linear-gradient(135deg, #a855f7 0%, #ec4899 50%, #f472b6 100%);
        -webkit-background-clip: text;
        background-clip: text;
        -webkit-text-fill-color: transparent;
        animation: gradientShift 8s ease infinite;
        background-size: 200% 200%;
    }

    @keyframes gradientShift {
        0%, 100% { background-position: 0% 50%; }
        50% { background-position: 100% 50%; }
    }

    .money-particle {
        position: absolute;
        width: 6px;
        height: 6px;
        background: radial-gradient(circle, rgba(251, 191, 36, 1), rgba(251, 191, 36, 0.3));
        border-radius: 50%;
        box-shadow: 0 0 8px rgba(251, 191, 36, 0.8);
        pointer-events: none;
        animation: flowIn 6s var(--delay) infinite ease-in;
        left: var(--start-x);
        top: var(--start-y);
        z-index: 20;
    }

    @keyframes flowIn {
        0% {
            opacity: 0;
            transform: translate(0, 0) scale(0.5);
        }
        10% {
            opacity: 1;
        }
        80% {
            opacity: 1;
        }
        100% {
            opacity: 0;
            transform: translate(
                calc(50% - var(--start-x)), 
                calc(50% - var(--start-y))
            ) scale(1.2);
        }
    }

    .activity-card {
        position: absolute;
        padding: 0.75rem 1rem;
        backdrop-filter: blur(20px);
        background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
        border: 1px solid rgba(255, 255, 255, 0.2);
        border-radius: 1rem;
        box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3), 0 0 20px rgba(168, 85, 247, 0.2);
        z-index: 25;
        animation: floatInOut 6s var(--delay) infinite ease-in-out;
        opacity: 0;
    }

    @keyframes floatInOut {
        0%, 100% {
            opacity: 0;
            transform: translateY(10px) scale(0.9);
        }
        10% {
            opacity: 1;
            transform: translateY(0) scale(1);
        }
        90% {
            opacity: 1;
            transform: translateY(0) scale(1);
        }
    }
</style>