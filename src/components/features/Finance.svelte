<script>
    import { CheckCircle2, ArrowDownLeft } from 'lucide-svelte';
</script>

<div class="flex flex-col md:flex-row items-center gap-16 reveal">
    <div class="flex-1 space-y-8">
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-green-500/30 bg-green-500/10 text-green-400 text-[10px] font-bold tracking-widest uppercase">
            Financial Automation
        </div>
        <h2 class="text-4xl md:text-6xl font-bold leading-tight text-white">Uang Masuk <br>Saat Anda Tidur.</h2>
        <p class="text-slate-400 text-lg leading-relaxed">
            Sistem pembayaran otomatis 24 jam. QRIS muncul instan, verifikasi otomatis via webhook, aktivasi VIP tanpa manual.
        </p>
        <ul class="feature-check space-y-3 mt-4 text-sm font-medium">
            <li>Integrasi Saweria & Trakteer</li>
            <li>QRIS Dinamis (Auto-Generate)</li>
            <li>Instant Settlement ke Wallet</li>
        </ul>
    </div>
    <div class="flex-1 w-full">
        <div class="glass-panel rounded-[3rem] p-8 relative rotate-2 hover:rotate-0 transition-transform duration-700 shadow-2xl border-t border-green-500/20 group">
            <div class="absolute inset-0 bg-gradient-to-tr from-green-500/10 to-transparent rounded-[3rem]"></div>
            
            <!-- Floating particles effect inside the card -->
            <div class="absolute top-10 right-10 w-20 h-20 bg-green-500/20 rounded-full blur-3xl animate-pulse"></div>

            <div class="space-y-4 relative z-10">
                <!-- Payment Notification 1 (Enhanced) -->
                <div class="glass-panel-dark rounded-2xl p-5 flex justify-between items-center border border-white/10 hover:bg-white/5 transition-colors cursor-default shadow-lg">
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 rounded-full bg-gradient-to-br from-green-500/20 to-emerald-900/20 border border-green-500/20 flex items-center justify-center text-green-400 shadow-[0_0_15px_rgba(74,222,128,0.1)]">
                            <ArrowDownLeft class="w-5 h-5" />
                        </div>
                        <div>
                            <div class="font-bold text-white text-base">Paket 30 Hari</div>
                            <div class="flex items-center gap-2 text-[10px] uppercase tracking-wider text-slate-400 font-medium">
                                <span class="w-1.5 h-1.5 rounded-full bg-green-500 animate-pulse"></span>
                                Success • via Trakteer
                            </div>
                        </div>
                    </div>
                    <div class="text-right">
                        <div class="font-bold text-green-400 text-lg tracking-tight">+Rp 35.000</div>
                        <div class="text-[10px] text-slate-500 font-medium">Just Now</div>
                    </div>
                </div>

                <!-- Payment Notification 2 (Enhanced) -->
                <div class="glass-panel-dark rounded-2xl p-5 flex justify-between items-center border border-white/5 opacity-60 hover:opacity-100 transition-opacity cursor-default">
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 rounded-full bg-white/5 border border-white/5 flex items-center justify-center text-slate-400">
                            <ArrowDownLeft class="w-5 h-5" />
                        </div>
                        <div>
                            <div class="font-bold text-slate-200 text-base">Paket 7 Hari</div>
                            <div class="text-[10px] uppercase tracking-wider text-slate-500 font-medium">Success • via Saweria</div>
                        </div>
                    </div>
                    <div class="text-right">
                        <div class="font-bold text-green-400/80 text-lg tracking-tight">+Rp 10.000</div>
                        <div class="text-[10px] text-slate-600 font-medium">2m ago</div>
                    </div>
                </div>
                
                <!-- Payment Notification 3 (Ghost Card for Depth) -->
                 <div class="glass-panel-dark rounded-2xl p-5 flex justify-between items-center border border-white/5 opacity-30 scale-95 origin-top">
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 rounded-full bg-white/5 flex items-center justify-center text-slate-500">
                            <ArrowDownLeft class="w-5 h-5" />
                        </div>
                        <div>
                            <div class="font-bold text-slate-400 text-base">Paket 30 Hari</div>
                        </div>
                    </div>
                    <div class="text-right">
                        <div class="font-bold text-slate-500 text-lg tracking-tight">+Rp 35.000</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>