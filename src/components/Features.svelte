<script>
    import Monetization from './features/Monetization.svelte';
    import Finance from './features/Finance.svelte';
    import Strategy from './features/Strategy.svelte';
    import Engagement from './features/Engagement.svelte';
    import Customization from './features/Customization.svelte';
    import Viral from './features/Viral.svelte';

    let mode = 'group'; // 'privacy' | 'group'

    function switchMode(newMode) {
        mode = newMode;
    }
</script>

<section id="features" class="py-20 px-4 relative z-10">
    <div class="max-w-6xl mx-auto space-y-48 md:space-y-32">
        <Monetization />
        <Finance />
        <Strategy {mode} {switchMode} />
        <Engagement />
        <Customization />
        <Viral />
    </div>
</section>