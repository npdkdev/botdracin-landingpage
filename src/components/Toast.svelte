<script>
    import { AlertCircle, CheckCircle, Info, XCircle } from 'lucide-svelte';
    
    export let message = '';
    export let type = 'info'; // 'success', 'error', 'warning', 'info'
    export let visible = false;
    export let duration = 3000;
    
    let timeoutId;
    
    $: if (visible) {
        clearTimeout(timeoutId);
        timeoutId = setTimeout(() => {
            visible = false;
        }, duration);
    }
    
    function close() {
        visible = false;
        clearTimeout(timeoutId);
    }
    
    const icons = {
        success: CheckCircle,
        error: XCircle,
        warning: AlertCircle,
        info: Info
    };
    
    const styles = {
        success: 'border-green-500/30 bg-green-500/10 text-green-300',
        error: 'border-red-500/30 bg-red-500/10 text-red-300',
        warning: 'border-amber-500/30 bg-amber-500/10 text-amber-300',
        info: 'border-blue-500/30 bg-blue-500/10 text-blue-300'
    };
    
    $: Icon = icons[type] || icons.info;
    $: styleClass = styles[type] || styles.info;
</script>

{#if visible}
<div 
    class="fixed top-4 right-4 z-50 glass-panel p-4 rounded-xl border backdrop-blur-xl shadow-2xl animate-slide-in max-w-md {styleClass}"
    role="alert"
>
    <div class="flex items-start gap-3">
        <Icon class="w-5 h-5 shrink-0 mt-0.5" />
        <p class="flex-1 text-sm font-medium">{message}</p>
        <button 
            on:click={close}
            class="shrink-0 text-white/40 hover:text-white/80 transition-colors"
            aria-label="Close notification"
        >
            <XCircle class="w-4 h-4" />
        </button>
    </div>
</div>
{/if}

<style>
    @keyframes slide-in {
        from {
            transform: translateX(100%);
            opacity: 0;
        }
        to {
            transform: translateX(0);
            opacity: 1;
        }
    }
    
    .animate-slide-in {
        animation: slide-in 0.3s ease-out;
    }
</style>
