<script>
    import { ChevronDown } from 'lucide-svelte';
</script>

<section id="faq" class="py-20 px-4 relative z-10">
    <div class="max-w-3xl mx-auto">
        <h2 class="text-4xl font-bold text-center mb-16 text-white reveal">Tanya Jawab</h2>
        <div class="space-y-4 reveal delay-100">
            
            <details class="glass-panel rounded-2xl group overflow-hidden">
                <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-6 text-white hover:bg-white/5 transition-colors">
                    <span class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-xs">01</div>
                        Apakah saya perlu skill coding?
                    </span>
                    <span class="transition-transform group-open:rotate-180">
                        <ChevronDown class="text-slate-400" />
                    </span>
                </summary>
                <div class="text-slate-400 px-6 pb-8 pt-2 ml-11 leading-relaxed text-sm border-t border-white/5">
                    YA, skill coding diperlukan untuk setup dan kustomisasi bot. Namun, kami menyediakan dokumentasi lengkap dan support untuk membantu Anda.
                </div>
            </details>

            <details class="glass-panel rounded-2xl group overflow-hidden">
                <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-6 text-white hover:bg-white/5 transition-colors">
                    <span class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-xs">02</div>
                        Apakah video disimpan di server saya?
                    </span>
                    <span class="transition-transform group-open:rotate-180">
                        <ChevronDown class="text-slate-400" />
                    </span>
                </summary>
                <div class="text-slate-400 px-6 pb-8 pt-2 ml-11 leading-relaxed text-sm border-t border-white/5">
                    TIDAK! Video disimpan di server Telegram (gratis & unlimited). Server VPS Anda hanya menyimpan data transaksi dan user, jadi sangat hemat biaya storage!
                </div>
            </details>

            <details class="glass-panel rounded-2xl group overflow-hidden">
                <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-6 text-white hover:bg-white/5 transition-colors">
                    <span class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-xs">03</div>
                        Berapa modal yang dibutuhkan?
                    </span>
                    <span class="transition-transform group-open:rotate-180">
                        <ChevronDown class="text-slate-400" />
                    </span>
                </summary>
                <div class="text-slate-400 px-6 pb-8 pt-2 ml-11 leading-relaxed text-sm border-t border-white/5">
                    Modal bervariasi mulai dari <strong class="text-white">500K hingga 3 juta rupiah</strong>, tergantung paket dan kebutuhan bisnis Anda. Investasi sekali bayar untuk software, plus biaya operasional VPS bulanan.
                </div>
            </details>

            <details class="glass-panel rounded-2xl group overflow-hidden">
                <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-6 text-white hover:bg-white/5 transition-colors">
                    <span class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-xs">04</div>
                        Bagaimana support & update?
                    </span>
                    <span class="transition-transform group-open:rotate-180">
                        <ChevronDown class="text-slate-400" />
                    </span>
                </summary>
                <div class="text-slate-400 px-6 pb-8 pt-2 ml-11 leading-relaxed text-sm border-t border-white/5">
                    Kami memberikan bantuan <strong class="text-white">selama masa berlangganan aktif</strong> dan update berkala untuk menjaga sistem tetap optimal dan aman.
                </div>
            </details>

            <details class="glass-panel rounded-2xl group overflow-hidden">
                <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-6 text-white hover:bg-white/5 transition-colors">
                    <span class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-xs">05</div>
                        Apa keuntungan dari program referral?
                    </span>
                    <span class="transition-transform group-open:rotate-180">
                        <ChevronDown class="text-slate-400" />
                    </span>
                </summary>
                <div class="text-slate-400 px-6 pb-8 pt-2 ml-11 leading-relaxed text-sm border-t border-white/5">
                    Setiap user mendapat <strong class="text-white">kode referral unik</strong> untuk mengajak teman. Komisi otomatis masuk ke wallet dan bisa ditarik kapan saja. Tracking lengkap tersedia di dashboard untuk monitoring performa referral Anda.
                </div>
            </details>

            <details class="glass-panel rounded-2xl group overflow-hidden">
                <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-6 text-white hover:bg-white/5 transition-colors">
                    <span class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-xs">06</div>
                        Bagaimana sistem pembayaran bekerja?
                    </span>
                    <span class="transition-transform group-open:rotate-180">
                        <ChevronDown class="text-slate-400" />
                    </span>
                </summary>
                <div class="text-slate-400 px-6 pb-8 pt-2 ml-11 leading-relaxed text-sm border-t border-white/5">
                    Pembayaran menggunakan <strong class="text-white">QRIS yang auto-generate</strong> (via Saweria/Trakteer). Setelah user scan dan bayar, sistem <strong class="text-white">otomatis memverifikasi</strong> pembayaran dan langsung mengaktifkan VIP—tanpa campur tangan manual!
                </div>
            </details>

            <details class="glass-panel rounded-2xl group overflow-hidden">
                <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-6 text-white hover:bg-white/5 transition-colors">
                    <span class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-xs">07</div>
                        Apa perbedaan Privacy Mode dan Watch Together?
                    </span>
                    <span class="transition-transform group-open:rotate-180">
                        <ChevronDown class="text-slate-400" />
                    </span>
                </summary>
                <div class="text-slate-400 px-6 pb-8 pt-2 ml-11 leading-relaxed text-sm border-t border-white/5">
                    <strong class="text-white">Privacy Mode:</strong> Video hanya bisa ditonton di chat pribadi dengan bot (maksimal content protection). <strong class="text-white">Watch Together:</strong> Video langsung play di grup untuk nonton bareng (viral marketing maksimal). Anda bisa toggle kapan saja dari Admin Panel.
                </div>
            </details>

            <details class="glass-panel rounded-2xl group overflow-hidden">
                <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-6 text-white hover:bg-white/5 transition-colors">
                    <span class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-xs">08</div>
                        Fitur apa saja yang ada di Admin Panel?
                    </span>
                    <span class="transition-transform group-open:rotate-180">
                        <ChevronDown class="text-slate-400" />
                    </span>
                </summary>
                <div class="text-slate-400 px-6 pb-8 pt-2 ml-11 leading-relaxed text-sm border-t border-white/5">
                    Dashboard overview lengkap dengan <strong class="text-white">revenue tracking, user management, package management, transaction monitoring, withdrawal approval, movie library, dan settings</strong>. Semua data real-time dengan grafik interaktif untuk memudahkan monitoring bisnis Anda.
                </div>
            </details>

        </div>
    </div>
</section>