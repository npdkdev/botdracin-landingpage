<script>
    import { CloudUpload, Users, Activity, MoreHorizontal } from 'lucide-svelte';
    
    let mockupHovered = false;
</script>

<section id="admin-panel" class="py-20 px-4 relative z-10">
    <div class="max-w-6xl mx-auto">
        <!-- Main Container -->
        <div class="glass-panel rounded-[3rem] p-8 md:p-16 relative overflow-hidden group reveal">
            
            <!-- Background Glows -->
            <div class="absolute top-0 left-0 w-[500px] h-[500px] bg-indigo-600/20 rounded-full blur-[120px] -translate-x-1/2 -translate-y-1/2 pointer-events-none"></div>
            <div class="absolute bottom-0 right-0 w-[500px] h-[500px] bg-fuchsia-600/10 rounded-full blur-[120px] translate-x-1/2 translate-y-1/2 pointer-events-none"></div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-20 items-center relative z-10">
                
                <!-- Left Content -->
                <div>
                    <div class="inline-block px-4 py-2 rounded-full border border-indigo-500/30 bg-indigo-500/10 text-indigo-300 text-sm font-semibold mb-6">
                        Admin Web Panel
                    </div>
                    
                    <h2 class="text-4xl md:text-5xl font-bold text-white mb-2 leading-tight">
                        Kontrol Penuh.
                    </h2>
                    <h2 class="text-4xl md:text-5xl font-bold text-slate-500 mb-6 leading-tight">
                        Tanpa Rumit.
                    </h2>
                    
                    <p class="text-slate-400 text-lg mb-10 leading-relaxed">
                        Dashboard admin berbasis web. Kelola film, user, dan keuangan tanpa menyentuh kode sedikitpun.
                    </p>

                    <!-- Feature List -->
                    <div class="space-y-8 mb-10">
                        <!-- Feature 1 -->
                        <div class="flex gap-5 group/item">
                            <div class="flex-shrink-0 w-12 h-12 rounded-2xl bg-white/5 border border-white/10 flex items-center justify-center group-hover/item:bg-indigo-500/20 group-hover/item:border-indigo-500/30 transition-all">
                                <CloudUpload class="w-6 h-6 text-indigo-400" />
                            </div>
                            <div>
                                <h3 class="text-lg font-bold text-white mb-1">Library & Pricing</h3>
                                <p class="text-slate-400 text-sm leading-relaxed">
                                    Upload film, atur episode, dan tentukan harga paket VIP sesuka hati.
                                </p>
                            </div>
                        </div>

                        <!-- Feature 2 -->
                        <div class="flex gap-5 group/item">
                            <div class="flex-shrink-0 w-12 h-12 rounded-2xl bg-white/5 border border-white/10 flex items-center justify-center group-hover/item:bg-fuchsia-500/20 group-hover/item:border-fuchsia-500/30 transition-all">
                                <Users class="w-6 h-6 text-fuchsia-400" />
                            </div>
                            <div>
                                <h3 class="text-lg font-bold text-white mb-1">Finance & User</h3>
                                <p class="text-slate-400 text-sm leading-relaxed">
                                    Pantau saldo user, history transaksi, dan approve penarikan komisi.
                                </p>
                            </div>
                        </div>

                        <!-- Feature 3 -->
                        <div class="flex gap-5 group/item">
                            <div class="flex-shrink-0 w-12 h-12 rounded-2xl bg-white/5 border border-white/10 flex items-center justify-center group-hover/item:bg-emerald-500/20 group-hover/item:border-emerald-500/30 transition-all">
                                <Activity class="w-6 h-6 text-emerald-400" />
                            </div>
                            <div>
                                <h3 class="text-lg font-bold text-white mb-1">Business Analytics</h3>
                                <p class="text-slate-400 text-sm leading-relaxed">
                                    Pantau revenue harian, pertumbuhan user, dan kesehatan bisnis.
                                </p>
                            </div>
                        </div>
                    </div>

                </div>

                <!-- Right Visual (Liquid Glass Dashboard Mockup) -->
                <div class="relative" 
                     on:mouseenter={() => mockupHovered = true}
                     on:mouseleave={() => mockupHovered = false}
                     role="presentation">
                    
                    <!-- Perspective Container -->
                    <div class="relative transition-all duration-700 ease-out {mockupHovered ? 'scale-105' : 'scale-100'}">
                        
                        <!-- Ambient Glows -->
                        <div class="absolute -top-20 -left-20 w-64 h-64 bg-indigo-500/30 rounded-full blur-[100px] opacity-60 transition-opacity duration-700 {mockupHovered ? 'opacity-80' : 'opacity-60'}"></div>
                        <div class="absolute -bottom-20 -right-20 w-80 h-80 bg-fuchsia-500/20 rounded-full blur-[120px] opacity-40 transition-opacity duration-700 {mockupHovered ? 'opacity-60' : 'opacity-40'}"></div>
                        
                        <!-- Device Frame - Liquid Glass -->
                        <div class="relative rounded-[2.5rem] p-6 backdrop-blur-[40px] bg-gradient-to-br from-white/[0.08] via-white/[0.03] to-white/[0.01] border border-white/[0.03] shadow-[0_8px_32px_rgba(0,0,0,0.4),inset_0_1px_1px_rgba(255,255,255,0.05)] transition-all duration-700 overflow-hidden {mockupHovered ? 'shadow-[0_20px_60px_rgba(99,102,241,0.3),inset_0_1px_1px_rgba(255,255,255,0.08)]' : ''}">
                            
                            <!-- Soft Reflection Gradient -->
                            <div class="absolute inset-0 rounded-[2.5rem] bg-gradient-to-tr from-white/[0.06] via-transparent to-white/[0.02] opacity-50 pointer-events-none"></div>
                            
                            <!-- Screen Content -->
                            <div class="relative space-y-5">
                                
                                <!-- Header Bar -->
                                <div class="flex items-center justify-between">
                                    <div class="flex gap-1.5">
                                        <div class="w-2.5 h-2.5 rounded-full bg-gradient-to-br from-red-400/80 to-red-500/60 shadow-[0_2px_8px_rgba(239,68,68,0.4)]"></div>
                                        <div class="w-2.5 h-2.5 rounded-full bg-gradient-to-br from-amber-400/80 to-amber-500/60 shadow-[0_2px_8px_rgba(245,158,11,0.4)]"></div>
                                        <div class="w-2.5 h-2.5 rounded-full bg-gradient-to-br from-emerald-400/80 to-emerald-500/60 shadow-[0_2px_8px_rgba(16,185,129,0.4)]"></div>
                                    </div>
                                    <div class="text-[9px] font-bold tracking-[0.15em] uppercase text-white/30">Dashboard</div>
                                </div>

                                <!-- Liquid Stat Droplets -->
                                <div class="grid grid-cols-2 gap-3">
                                    <!-- Revenue Droplet -->
                                    <div class="group/stat relative rounded-[1.25rem] p-4 backdrop-blur-[30px] bg-gradient-to-br from-indigo-500/[0.12] via-indigo-500/[0.06] to-transparent border border-indigo-400/[0.08] shadow-[0_4px_16px_rgba(99,102,241,0.15),inset_0_1px_0_rgba(255,255,255,0.03)] transition-all duration-500 hover:shadow-[0_8px_24px_rgba(99,102,241,0.25),inset_0_1px_0_rgba(255,255,255,0.06)] hover:border-indigo-400/[0.15]">
                                        <div class="absolute inset-0 rounded-[1.25rem] bg-gradient-to-br from-white/[0.04] to-transparent opacity-0 group-hover/stat:opacity-100 transition-opacity duration-500"></div>
                                        <div class="relative">
                                            <div class="text-[10px] text-white/40 mb-1.5 font-medium">Revenue</div>
                                            <div class="text-lg font-bold text-white tracking-tight">Rp 4.5M</div>
                                        </div>
                                    </div>

                                    <!-- Users Droplet -->
                                    <div class="group/stat relative rounded-[1.25rem] p-4 backdrop-blur-[30px] bg-gradient-to-br from-emerald-500/[0.12] via-emerald-500/[0.06] to-transparent border border-emerald-400/[0.08] shadow-[0_4px_16px_rgba(16,185,129,0.15),inset_0_1px_0_rgba(255,255,255,0.03)] transition-all duration-500 hover:shadow-[0_8px_24px_rgba(16,185,129,0.25),inset_0_1px_0_rgba(255,255,255,0.06)] hover:border-emerald-400/[0.15]">
                                        <div class="absolute inset-0 rounded-[1.25rem] bg-gradient-to-br from-white/[0.04] to-transparent opacity-0 group-hover/stat:opacity-100 transition-opacity duration-500"></div>
                                        <div class="relative">
                                            <div class="text-[10px] text-white/40 mb-1.5 font-medium">Active VIP</div>
                                            <div class="text-lg font-bold text-emerald-300 tracking-tight">342</div>
                                        </div>
                                    </div>
                                </div>

                                <!-- Liquid Chart Bubble -->
                                <div class="relative rounded-[1.5rem] p-5 backdrop-blur-[35px] bg-gradient-to-br from-white/[0.06] via-white/[0.02] to-white/[0.01] border border-white/[0.04] shadow-[0_8px_24px_rgba(0,0,0,0.2),inset_0_1px_1px_rgba(255,255,255,0.04)]">
                                    
                                    <!-- Soft Inner Glow -->
                                    <div class="absolute inset-0 rounded-[1.5rem] bg-gradient-to-tr from-indigo-500/[0.08] via-transparent to-fuchsia-500/[0.05] opacity-60 pointer-events-none"></div>
                                    
                                    <!-- Chart Content -->
                                    <div class="relative h-40 flex items-end justify-between gap-2">
                                        <!-- Grid Lines -->
                                        <div class="absolute inset-0 flex flex-col justify-between opacity-[0.06] pointer-events-none">
                                            <div class="w-full h-px bg-white"></div>
                                            <div class="w-full h-px bg-white"></div>
                                            <div class="w-full h-px bg-white"></div>
                                            <div class="w-full h-px bg-white"></div>
                                        </div>

                                        <!-- Liquid Bars -->
                                        <div class="group/bar relative flex-1 rounded-t-[0.75rem] bg-gradient-to-t from-indigo-500/30 via-indigo-500/20 to-indigo-500/10 h-[28%] transition-all duration-500 hover:from-indigo-400/40 hover:via-indigo-400/30 hover:to-indigo-400/15 hover:shadow-[0_0_20px_rgba(99,102,241,0.3)]">
                                            <div class="absolute inset-x-0 top-0 h-1/2 bg-gradient-to-b from-white/[0.08] to-transparent rounded-t-[0.75rem]"></div>
                                        </div>
                                        <div class="group/bar relative flex-1 rounded-t-[0.75rem] bg-gradient-to-t from-indigo-500/40 via-indigo-500/28 to-indigo-500/15 h-[48%] transition-all duration-500 hover:from-indigo-400/50 hover:via-indigo-400/38 hover:to-indigo-400/20 hover:shadow-[0_0_20px_rgba(99,102,241,0.3)]">
                                            <div class="absolute inset-x-0 top-0 h-1/2 bg-gradient-to-b from-white/[0.08] to-transparent rounded-t-[0.75rem]"></div>
                                        </div>
                                        <div class="group/bar relative flex-1 rounded-t-[0.75rem] bg-gradient-to-t from-indigo-500/35 via-indigo-500/24 to-indigo-500/12 h-[38%] transition-all duration-500 hover:from-indigo-400/45 hover:via-indigo-400/34 hover:to-indigo-400/18 hover:shadow-[0_0_20px_rgba(99,102,241,0.3)]">
                                            <div class="absolute inset-x-0 top-0 h-1/2 bg-gradient-to-b from-white/[0.08] to-transparent rounded-t-[0.75rem]"></div>
                                        </div>
                                        <div class="group/bar relative flex-1 rounded-t-[0.75rem] bg-gradient-to-t from-indigo-500/55 via-indigo-500/40 to-indigo-500/22 h-[68%] shadow-[0_0_16px_rgba(99,102,241,0.25)] transition-all duration-500 hover:from-indigo-400/65 hover:via-indigo-400/50 hover:to-indigo-400/28 hover:shadow-[0_0_24px_rgba(99,102,241,0.4)]">
                                            <div class="absolute inset-x-0 top-0 h-1/2 bg-gradient-to-b from-white/[0.12] to-transparent rounded-t-[0.75rem]"></div>
                                        </div>
                                        <div class="group/bar relative flex-1 rounded-t-[0.75rem] bg-gradient-to-t from-indigo-500/45 via-indigo-500/32 to-indigo-500/18 h-[58%] transition-all duration-500 hover:from-indigo-400/55 hover:via-indigo-400/42 hover:to-indigo-400/24 hover:shadow-[0_0_20px_rgba(99,102,241,0.3)]">
                                            <div class="absolute inset-x-0 top-0 h-1/2 bg-gradient-to-b from-white/[0.08] to-transparent rounded-t-[0.75rem]"></div>
                                        </div>
                                        <div class="group/bar relative flex-1 rounded-t-[0.75rem] bg-gradient-to-t from-indigo-500/70 via-indigo-500/55 to-indigo-500/30 h-[82%] shadow-[0_0_20px_rgba(99,102,241,0.35)] transition-all duration-500 hover:from-indigo-400/80 hover:via-indigo-400/65 hover:to-indigo-400/38 hover:shadow-[0_0_28px_rgba(99,102,241,0.5)]">
                                            <div class="absolute inset-x-0 top-0 h-1/2 bg-gradient-to-b from-white/[0.15] to-transparent rounded-t-[0.75rem]"></div>
                                        </div>
                                    </div>
                                </div>

                                <!-- Liquid Activity Feed -->
                                <div class="space-y-2">
                                    <!-- Activity Item 1 -->
                                    <div class="relative rounded-[1rem] p-3 backdrop-blur-[25px] bg-gradient-to-r from-white/[0.04] to-transparent border border-white/[0.03] shadow-[0_2px_8px_rgba(0,0,0,0.15),inset_0_0.5px_0_rgba(255,255,255,0.02)] transition-all duration-300 hover:border-white/[0.06] hover:shadow-[0_4px_12px_rgba(0,0,0,0.2)]">
                                        <div class="flex items-center gap-2.5">
                                            <div class="w-1.5 h-1.5 rounded-full bg-gradient-to-br from-emerald-400 to-emerald-500 shadow-[0_0_8px_rgba(16,185,129,0.6)]"></div>
                                            <div class="flex-1">
                                                <div class="text-[10px] text-white/60 leading-tight">New VIP Subscription</div>
                                            </div>
                                            <div class="text-[9px] text-white/30">2m ago</div>
                                        </div>
                                    </div>

                                    <!-- Activity Item 2 -->
                                    <div class="relative rounded-[1rem] p-3 backdrop-blur-[25px] bg-gradient-to-r from-white/[0.04] to-transparent border border-white/[0.03] shadow-[0_2px_8px_rgba(0,0,0,0.15),inset_0_0.5px_0_rgba(255,255,255,0.02)] transition-all duration-300 hover:border-white/[0.06] hover:shadow-[0_4px_12px_rgba(0,0,0,0.2)]">
                                        <div class="flex items-center gap-2.5">
                                            <div class="w-1.5 h-1.5 rounded-full bg-gradient-to-br from-blue-400 to-blue-500 shadow-[0_0_8px_rgba(59,130,246,0.6)]"></div>
                                            <div class="flex-1">
                                                <div class="text-[10px] text-white/60 leading-tight">Payment Received</div>
                                            </div>
                                            <div class="text-[9px] text-white/30">5m ago</div>
                                        </div>
                                    </div>
                                </div>

                            </div>

                            <!-- Floating Payment Bubble -->
                            <div class="absolute -bottom-4 -right-4 rounded-[1.25rem] px-4 py-2.5 backdrop-blur-[40px] bg-gradient-to-br from-fuchsia-500/[0.15] via-fuchsia-500/[0.08] to-transparent border border-fuchsia-400/[0.12] shadow-[0_8px_24px_rgba(217,70,239,0.25),inset_0_1px_0_rgba(255,255,255,0.06)] transition-all duration-700 {mockupHovered ? 'translate-y-0 opacity-100' : 'translate-y-2 opacity-80'}">
                                <div class="absolute inset-0 rounded-[1.25rem] bg-gradient-to-br from-white/[0.08] to-transparent"></div>
                                <div class="relative flex items-center gap-2">
                                    <div class="text-[10px] text-white/50 font-medium">Today</div>
                                    <div class="text-sm font-bold text-fuchsia-300">+Rp 850k</div>
                                </div>
                            </div>
                            
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</section>