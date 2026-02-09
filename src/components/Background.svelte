<div class="noise-bg"></div>
    
<div class="ambient-light">
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
    <div class="orb orb-3"></div>
    <div class="orb orb-4"></div>
</div>

<style>
    .noise-bg {
        position: fixed;
        top: 0; 
        left: 0; 
        width: 100%; 
        height: 100%;
        background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' opacity='0.03'/%3E%3C/svg%3E");
        pointer-events: none;
        z-index: 0;
    }

    .ambient-light {
        position: fixed;
        width: 100vw;
        height: 100vh;
        top: 0;
        left: 0;
        z-index: -1;
        overflow: hidden;
        pointer-events: none;
    }

    .orb {
        position: absolute;
        border-radius: 50%;
        filter: blur(120px);
        opacity: 0.5;
        animation: float 20s infinite ease-in-out;
        mix-blend-mode: screen;
    }

    /* Indigo orb - top left */
    .orb-1 { 
        width: 700px; 
        height: 700px; 
        background: radial-gradient(circle, #6366f1 0%, #4f46e5 50%, transparent 100%);
        top: -15%; 
        left: -10%; 
        animation-delay: 0s;
    }

    /* Purple/Fuchsia orb - bottom right */
    .orb-2 { 
        width: 600px; 
        height: 600px; 
        background: radial-gradient(circle, #d946ef 0%, #c026d3 50%, transparent 100%);
        bottom: -10%; 
        right: -8%; 
        animation-delay: -5s;
    }

    /* Cyan orb - center */
    .orb-3 { 
        width: 500px; 
        height: 500px; 
        background: radial-gradient(circle, #22d3ee 0%, #06b6d4 50%, transparent 100%);
        top: 35%; 
        left: 25%; 
        opacity: 0.35;
        animation-delay: -10s;
    }

    /* Fuchsia accent orb - top right */
    .orb-4 { 
        width: 450px; 
        height: 450px; 
        background: radial-gradient(circle, #f0abfc 0%, #e879f9 50%, transparent 100%);
        top: 10%; 
        right: 15%; 
        opacity: 0.4;
        animation-delay: -15s;
    }

    @keyframes float {
        0%, 100% { 
            transform: translate(0, 0) scale(1); 
        }
        25% { 
            transform: translate(30px, -50px) scale(1.05); 
        }
        50% { 
            transform: translate(-20px, -30px) scale(0.95); 
        }
        75% { 
            transform: translate(40px, 20px) scale(1.02); 
        }
    }
</style>