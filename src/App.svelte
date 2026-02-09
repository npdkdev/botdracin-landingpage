<script>
    import { onMount, onDestroy } from 'svelte';
    import Background from './components/Background.svelte';
    import Navbar from './components/Navbar.svelte';
    import Hero from './components/Hero.svelte';
    import AiPlanner from './components/AiPlanner.svelte';
    import Ecosystem from './components/Ecosystem.svelte';
    import AdminPanel from './components/AdminPanel.svelte';
    import Features from './components/Features.svelte';
    import Pricing from './components/Pricing.svelte';
    import RentalPricing from './components/RentalPricing.svelte';
    import Faq from './components/Faq.svelte';
    import Footer from './components/Footer.svelte';

    let observer;

    // Scroll Reveal Logic
    onMount(() => {
        const observerOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -50px 0px"
        };

        observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, observerOptions);

        // Delay slightly to ensure DOM is ready for observation
        setTimeout(() => {
            document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
        }, 100);
    });
    
    onDestroy(() => {
        // Clean up observer
        if (observer) {
            observer.disconnect();
            observer = null;
        }
    });
</script>

<Background />
<Navbar />
<Hero />
<AiPlanner />
<Ecosystem />
<AdminPanel />
<Features />
<Pricing />
<RentalPricing />
<Faq />
<Footer />