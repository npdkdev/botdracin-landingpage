<script>
    import { QrCode, CheckCircle, Zap, Eye, Crown, User } from 'lucide-svelte';
</script>

<section id="superior" class="py-32 px-4 relative z-10">
    <div class="max-w-6xl mx-auto">
        <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-6 reveal">
            <div class="text-left">
                <h2 class="text-4xl font-bold mb-4 text-white">Fitur Unggulan</h2>
                <p class="text-white/50 max-w-md">Teknologi otomasi yang bekerja 24 jam untuk Anda.</p>
            </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <!-- Auto Payment Feature -->
            <div class="glass-panel rounded-[3rem] p-10 flex flex-col justify-between min-h-[500px] relative overflow-hidden group reveal hover:-translate-y-2 transition-all duration-300 border border-white/5 hover:border-green-500/30">
                <div class="absolute top-0 right-0 p-10 opacity-20 group-hover:opacity-40 transition-opacity">
                    <QrCode class="w-32 h-32 text-white" />
                </div>
                
                <div class="relative z-10">
                    <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white/5 border border-white/10 text-xs font-medium text-white/70 mb-4">
                        Saweria & Trakteer Ready
                    </div>
                    <h3 class="text-3xl font-bold mb-4 text-white">Auto-Payment & QRIS</h3>
                    <p class="text-white/60 text-lg leading-relaxed max-w-sm">
                        Tidak perlu cek mutasi manual. Sistem otomatis generate QRIS, verifikasi pembayaran, dan mengaktifkan VIP user dalam hitungan detik.
                    </p>
                    <ul class="mt-6 space-y-2 text-sm text-white/50">
                        <li class="flex items-center gap-2"><CheckCircle class="w-4 h-4 text-green-400" /> Auto-Generate QR Code</li>
                        <li class="flex items-center gap-2"><CheckCircle class="w-4 h-4 text-green-400" /> Auto-Verify via Webhook</li>
                        <li class="flex items-center gap-2"><CheckCircle class="w-4 h-4 text-green-400" /> Instant Activation</li>
                    </ul>
                </div>

                <!-- UI Mockup -->
                <div class="glass-panel rounded-2xl p-5 bg-black/20 mt-8 backdrop-blur-md border-t border-white/10 group-hover:scale-[1.02] transition-transform">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-sm font-medium text-white/70">Status Transaksi</span>
                        <span class="px-2 py-0.5 rounded bg-green-500/20 text-green-400 text-[10px] font-bold border border-green-500/20">PAID</span>
                    </div>
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-full bg-indigo-500/20 flex items-center justify-center border border-indigo-500/30">
                            <Zap class="text-indigo-400 w-5 h-5" />
                        </div>
                        <div>
                            <div class="text-sm font-bold text-white">Paket 30 Hari</div>
                            <div class="text-xs text-white/40">Rp 35.000 • Trakteer</div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Watch Strategy Feature -->
            <div class="glass-panel rounded-[3rem] p-10 flex flex-col justify-between min-h-[500px] relative overflow-hidden group reveal delay-100 hover:-translate-y-2 transition-all duration-300 border border-white/5 hover:border-indigo-500/30">
                 <div class="absolute top-0 right-0 p-10 opacity-20 group-hover:opacity-40 transition-opacity">
                    <Eye class="w-32 h-32 text-white" />
                </div>

                <div class="relative z-10">
                    <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white/5 border border-white/10 text-xs font-medium text-white/70 mb-4">
                        2 Mode Strategis
                    </div>
                    <h3 class="text-3xl font-bold mb-4 text-white">Privacy vs Watch Together</h3>
                    <p class="text-white/60 text-lg leading-relaxed max-w-sm">
                        Anda yang tentukan cara user menonton. Eksklusif di chat pribadi atau viral di grup komunitas.
                    </p>
                    
                    <div class="mt-6 space-y-4">
                        <div class="glass-panel p-4 rounded-xl bg-white/5 border-l-2 border-l-red-400 group-hover:bg-white/10 transition-colors">
                            <h4 class="text-sm font-bold text-white mb-1">🔒 Privacy Mode (Default)</h4>
                            <p class="text-xs text-white/50 leading-relaxed">Video hanya bisa ditonton di Private Chat dengan Bot. Maksimal proteksi konten.</p>
                        </div>
                        <div class="glass-panel p-4 rounded-xl bg-white/5 border-l-2 border-l-green-400 group-hover:bg-white/10 transition-colors">
                            <h4 class="text-sm font-bold text-white mb-1">👥 Watch Together Mode</h4>
                            <p class="text-xs text-white/50 leading-relaxed">Video langsung play di Grup. Semua member grup bisa nonton bareng. Viral marketing!</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Viral Referral Feature (Full Width) -->
            <div class="glass-panel rounded-[3rem] p-10 md:col-span-2 flex flex-col md:flex-row items-center gap-10 relative overflow-hidden group reveal delay-200 hover:-translate-y-2 transition-all duration-300 border border-white/5 hover:border-yellow-500/30">
                <div class="absolute -right-20 -bottom-20 w-96 h-96 bg-yellow-500/5 rounded-full blur-[100px] group-hover:bg-yellow-500/10 transition-colors"></div>
                
                <div class="flex-1 relative z-10">
                    <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white/5 border border-white/10 text-xs font-medium text-white/70 mb-4">
                        Zero Marketing Cost
                    </div>
                    <h3 class="text-3xl font-bold mb-4 text-white">Sistem Referral Viral</h3>
                    <p class="text-white/60 text-lg leading-relaxed mb-8">
                        Biarkan user bekerja untuk Anda. Setiap user memiliki kode unik. Saat mereka mengajak teman membeli VIP, mereka mendapat komisi (masuk wallet) dan Anda mendapat customer baru gratis.
                    </p>
                    <div class="flex gap-8 items-center">
                        <div class="text-center group-hover:scale-110 transition-transform">
                            <div class="text-3xl font-black text-white mb-1">20%</div>
                            <div class="text-[10px] font-bold text-white/40 uppercase tracking-widest">Komisi User</div>
                        </div>
                        <div class="w-px h-12 bg-white/10"></div>
                        <div class="text-center group-hover:scale-110 transition-transform delay-75">
                            <div class="text-3xl font-black text-white mb-1">∞</div>
                            <div class="text-[10px] font-bold text-white/40 uppercase tracking-widest">Potensi User</div>
                        </div>
                    </div>
                </div>
                
                <!-- Abstract Visualization of Network -->
                <div class="flex-1 w-full relative h-64 md:h-auto flex items-center justify-center min-h-[250px]">
                    <div class="relative w-full max-w-sm h-full flex items-center justify-center">
                        <!-- Center Node (You) -->
                        <div class="absolute w-20 h-20 rounded-full glass-panel flex items-center justify-center z-20 border border-yellow-500/30 shadow-[0_0_50px_rgba(234,179,8,0.2)] bg-black/40 backdrop-blur-xl group-hover:scale-110 transition-transform duration-500">
                            <Crown class="w-8 h-8 text-yellow-400 fill-yellow-400/20" />
                        </div>
                        
                        <!-- Satellites -->
                        <div class="absolute left-[15%] top-[20%] w-12 h-12 rounded-full glass-panel flex items-center justify-center animate-pulse border border-white/10 bg-black/40">
                            <User class="w-5 h-5 text-white/50" />
                        </div>
                        <div class="absolute right-[15%] bottom-[20%] w-12 h-12 rounded-full glass-panel flex items-center justify-center animate-pulse delay-700 border border-white/10 bg-black/40">
                            <User class="w-5 h-5 text-white/50" />
                        </div>
                        <div class="absolute right-[20%] top-[15%] w-12 h-12 rounded-full glass-panel flex items-center justify-center animate-pulse delay-300 border border-white/10 bg-black/40">
                            <User class="w-5 h-5 text-white/50" />
                        </div>
                        
                        <!-- Connecting Lines (SVG) -->
                        <svg class="absolute inset-0 w-full h-full pointer-events-none opacity-30" style="z-index: 0;">
                            <!-- Lines from center to satellites -->
                             <line x1="50%" y1="50%" x2="20%" y2="25%" stroke="url(#gradient-line)" stroke-width="2" />
                             <line x1="50%" y1="50%" x2="80%" y2="75%" stroke="url(#gradient-line)" stroke-width="2" />
                             <line x1="50%" y1="50%" x2="75%" y2="20%" stroke="url(#gradient-line)" stroke-width="2" />
                             
                             <defs>
                                <linearGradient id="gradient-line" x1="0%" y1="0%" x2="100%" y2="0%">
                                    <stop offset="0%" stop-color="rgba(255,255,255,0)" />
                                    <stop offset="50%" stop-color="rgba(234,179,8,0.5)" />
                                    <stop offset="100%" stop-color="rgba(255,255,255,0)" />
                                </linearGradient>
                             </defs>
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>