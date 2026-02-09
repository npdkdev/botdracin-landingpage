<script>
    import { Lock, LockOpen, Sparkles, TrendingUp } from 'lucide-svelte';
    
    let freeParts = 1;
    let isDragging = false;
    
    const episodes = [
        { id: 1, title: "Pilot: The Beginning", duration: "45:23" },
        { id: 2, title: "Rising Tensions", duration: "42:18" },
        { id: 3, title: "Breaking Point", duration: "48:55" },
        { id: 4, title: "Revelations", duration: "51:42" },
        { id: 5, title: "Final Showdown", duration: "55:30" }
    ];
    
    function handleSliderChange(e) {
        freeParts = parseInt(e.target.value);
    }
    
    function isUnlocked(episodeId) {
        return episodeId <= freeParts;
    }
</script>

<div class="flex flex-col md:flex-row items-stretch gap-16 reveal">
    <!-- Left Content -->
    <div class="flex-1 flex flex-col justify-center space-y-8">
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-amber-500/30 bg-amber-500/10 text-amber-400 text-[10px] font-bold tracking-widest uppercase w-fit">
            Monetization Engine
        </div>
        <h2 class="text-4xl md:text-6xl font-bold leading-tight text-white">
            Pancing dengan <br>Gratis. Jualan <span class="bg-gradient-to-r from-amber-400 to-orange-500 bg-clip-text text-transparent">VIP</span>.
        </h2>
        <p class="text-slate-400 text-lg leading-relaxed max-w-lg">
            Biarkan user mencicipi <strong class="text-amber-400">1 episode gratis</strong>. Saat mereka ketagihan, 
            konversi jadi member VIP. Preview gratis yang bikin penasaran = conversion rate maksimal.
        </p>
        
        <!-- Conversion Stats -->
        <div class="grid grid-cols-2 gap-4 mt-6">
            <div class="glass-panel rounded-2xl p-5 border border-white/5 hover:border-amber-500/20 transition-all duration-300 group">
                <div class="flex items-center gap-2 mb-2">
                    <TrendingUp class="w-4 h-4 text-amber-400 group-hover:scale-110 transition-transform" />
                    <div class="text-[10px] text-slate-500 font-bold uppercase tracking-wider">Conversion</div>
                </div>
                <div class="text-3xl font-bold text-white">37%</div>
                <div class="text-xs text-emerald-400 mt-1">+12% vs no preview</div>
            </div>
            <div class="glass-panel rounded-2xl p-5 border border-white/5 hover:border-amber-500/20 transition-all duration-300 group">
                <div class="flex items-center gap-2 mb-2">
                    <Sparkles class="w-4 h-4 text-amber-400 group-hover:rotate-12 transition-transform" />
                    <div class="text-[10px] text-slate-500 font-bold uppercase tracking-wider">Revenue</div>
                </div>
                <div class="text-3xl font-bold text-white">2.8x</div>
                <div class="text-xs text-emerald-400 mt-1">with free preview</div>
            </div>
        </div>
    </div>

    <!-- Right Interactive Preview -->
    <div class="flex-1 relative">
        <!-- Background Gradient -->
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_center,rgba(251,191,36,0.08),transparent_70%)] rounded-3xl"></div>
        
        <!-- Main Container -->
        <div class="relative glass-panel rounded-[2.5rem] p-8 border border-amber-500/20 shadow-[0_30px_60px_rgba(251,191,36,0.1)]">
            
            <!-- Header -->
            <div class="mb-6 pb-6 border-b border-white/10">
                <div class="flex items-center justify-between mb-4">
                    <h3 class="text-xl font-bold text-white">Free Preview Simulator</h3>
                    <div class="px-3 py-1 rounded-full bg-amber-500/10 border border-amber-500/30 text-amber-400 text-xs font-bold">
                        LIVE
                    </div>
                </div>
                
                <!-- Slider Control -->
                <div class="space-y-3">
                    <div class="flex items-center justify-between text-sm">
                        <span class="text-slate-400 font-medium">Free Episodes:</span>
                        <span class="text-2xl font-bold text-amber-400">{freeParts}</span>
                    </div>
                    <div class="relative">
                        <input 
                            type="range" 
                            min="0" 
                            max="5" 
                            bind:value={freeParts}
                            on:input={handleSliderChange}
                            on:mousedown={() => isDragging = true}
                            on:mouseup={() => isDragging = false}
                            class="w-full h-2 bg-white/5 rounded-full appearance-none cursor-pointer
                                   [&::-webkit-slider-thumb]:appearance-none
                                   [&::-webkit-slider-thumb]:w-6
                                   [&::-webkit-slider-thumb]:h-6
                                   [&::-webkit-slider-thumb]:rounded-full
                                   [&::-webkit-slider-thumb]:bg-gradient-to-br
                                   [&::-webkit-slider-thumb]:from-amber-400
                                   [&::-webkit-slider-thumb]:to-orange-500
                                   [&::-webkit-slider-thumb]:border-2
                                   [&::-webkit-slider-thumb]:border-white/20
                                   [&::-webkit-slider-thumb]:shadow-[0_0_20px_rgba(251,191,36,0.5)]
                                   [&::-webkit-slider-thumb]:cursor-grab
                                   [&::-webkit-slider-thumb]:active:cursor-grabbing
                                   [&::-webkit-slider-thumb]:hover:scale-110
                                   [&::-webkit-slider-thumb]:transition-transform
                                   [&::-moz-range-thumb]:w-6
                                   [&::-moz-range-thumb]:h-6
                                   [&::-moz-range-thumb]:rounded-full
                                   [&::-moz-range-thumb]:bg-gradient-to-br
                                   [&::-moz-range-thumb]:from-amber-400
                                   [&::-moz-range-thumb]:to-orange-500
                                   [&::-moz-range-thumb]:border-2
                                   [&::-moz-range-thumb]:border-white/20
                                   [&::-moz-range-thumb]:cursor-grab
                                   [&::-moz-range-thumb]:active:cursor-grabbing
                                   hover:bg-white/10 transition-all"
                            style="background: linear-gradient(to right, 
                                rgba(251,191,36,0.3) 0%, 
                                rgba(251,191,36,0.3) {(freeParts / 5) * 100}%, 
                                rgba(255,255,255,0.05) {(freeParts / 5) * 100}%, 
                                rgba(255,255,255,0.05) 100%)"
                        />
                        <!-- Tick marks -->
                        <div class="absolute -bottom-5 left-0 right-0 flex justify-between px-3 pointer-events-none">
                            {#each [0,1,2,3,4,5] as tick}
                                <div class="text-[9px] text-slate-600 font-bold">{tick}</div>
                            {/each}
                        </div>
                    </div>
                </div>
            </div>

            <!-- Episodes List -->
            <div class="space-y-3">
                {#each episodes as episode}
                    {@const unlocked = isUnlocked(episode.id)}
                    <div 
                        class="glass-panel-dark rounded-2xl p-4 border transition-all duration-500 group
                               {unlocked 
                                 ? 'border-emerald-500/30 bg-emerald-500/5 hover:border-emerald-500/50 hover:bg-emerald-500/10' 
                                 : 'border-red-500/20 bg-red-500/5 hover:border-red-500/30'}"
                        style="transition-delay: {episode.id * 50}ms"
                    >
                        <div class="flex items-center gap-4">
                            <!-- Lock/Unlock Icon -->
                            <div class="w-12 h-12 rounded-xl flex items-center justify-center border transition-all duration-500
                                        {unlocked 
                                          ? 'bg-emerald-500/20 border-emerald-500/40 group-hover:bg-emerald-500/30 group-hover:shadow-[0_0_20px_rgba(16,185,129,0.3)]' 
                                          : 'bg-red-500/20 border-red-500/40 backdrop-blur-sm group-hover:bg-red-500/30'}">
                                {#if unlocked}
                                    <LockOpen class="w-6 h-6 text-emerald-400 group-hover:scale-110 transition-transform" />
                                {:else}
                                    <Lock class="w-6 h-6 text-red-400 group-hover:shake transition-all" />
                                {/if}
                            </div>
                            
                            <!-- Episode Info -->
                            <div class="flex-1 min-w-0">
                                <div class="flex items-center gap-2 mb-1">
                                    <div class="text-xs font-bold {unlocked ? 'text-emerald-400' : 'text-red-400'} uppercase tracking-wider">
                                        Episode {episode.id}
                                    </div>
                                    {#if !unlocked}
                                        <div class="px-2 py-0.5 rounded-full bg-red-500/20 border border-red-500/30 text-[9px] text-red-300 font-bold uppercase tracking-wider">
                                            VIP Only
                                        </div>
                                    {/if}
                                </div>
                                <div class="text-white font-semibold truncate {!unlocked ? 'blur-[2px] select-none' : ''}">
                                    {episode.title}
                                </div>
                                <div class="text-xs text-slate-500 font-medium mt-0.5">
                                    {episode.duration}
                                </div>
                            </div>

                            <!-- Status Badge -->
                            <div class="flex-shrink-0">
                                {#if unlocked}
                                    <div class="px-3 py-1.5 rounded-lg bg-emerald-500/10 border border-emerald-500/30 text-emerald-400 text-xs font-bold uppercase tracking-wider">
                                        Free
                                    </div>
                                {:else}
                                    <div class="px-3 py-1.5 rounded-lg bg-gradient-to-r from-amber-500/20 to-orange-500/20 border border-amber-500/30 text-amber-400 text-xs font-bold uppercase tracking-wider shadow-[0_0_15px_rgba(251,191,36,0.2)]">
                                        Upgrade
                                    </div>
                                {/if}
                            </div>
                        </div>
                    </div>
                {/each}
            </div>

            <!-- Bottom CTA -->
            <div class="mt-6 pt-6 border-t border-white/10">
                <div class="glass-panel rounded-2xl p-4 border border-amber-500/20 bg-gradient-to-br from-amber-500/5 to-orange-500/5">
                    <div class="flex items-center justify-between">
                        <div class="flex-1">
                            <div class="text-sm font-bold text-white mb-1">
                                {#if freeParts === 0}
                                    No preview? Zero conversions.
                                {:else if freeParts === 1}
                                    Perfect! Tease mereka dengan 1 episode.
                                {:else if freeParts <= 3}
                                    Good balance untuk build hype.
                                {:else}
                                    Terlalu banyak gratis = revenue drop.
                                {/if}
                            </div>
                            <div class="text-xs text-slate-400">
                                {freeParts === 0 ? 'User butuh preview sebelum beli' : 
                                 freeParts === 1 ? 'Sweet spot untuk maksimal konversi' :
                                 freeParts <= 3 ? 'Masih profitable tapi kurang urgent' :
                                 'User puas gratis, ga ada urgency beli'}
                            </div>
                        </div>
                        <div class="text-right">
                            <div class="text-2xl font-bold bg-gradient-to-r from-amber-400 to-orange-500 bg-clip-text text-transparent">
                                {freeParts === 0 ? '0%' :
                                 freeParts === 1 ? '37%' :
                                 freeParts === 2 ? '31%' :
                                 freeParts === 3 ? '24%' :
                                 freeParts === 4 ? '15%' :
                                 '8%'}
                            </div>
                            <div class="text-[9px] text-slate-500 font-bold uppercase tracking-wider">CVR</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Floating Decorative Elements -->
        <div class="absolute -top-4 -right-4 w-24 h-24 bg-amber-500/10 rounded-full blur-3xl opacity-60 animate-pulse" style="animation-duration: 3s;"></div>
        <div class="absolute -bottom-6 -left-6 w-32 h-32 bg-orange-500/10 rounded-full blur-3xl opacity-50 animate-pulse" style="animation-duration: 5s; animation-delay: 1s;"></div>
    </div>
</div>

<style>
    @keyframes shake {
        0%, 100% { transform: rotate(0deg); }
        25% { transform: rotate(-5deg); }
        75% { transform: rotate(5deg); }
    }
    
    .group:hover .shake {
        animation: shake 0.5s ease-in-out;
    }
</style>
