<script>
import '../styles/globals.css'

export const ssr = false;
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Patrick+Hand&display=swap" rel="stylesheet">
</svelte:head>

<div class="container mx-auto px-36 py-8">
    <slot />
</div>