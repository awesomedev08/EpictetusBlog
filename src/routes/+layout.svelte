<script>
	import Footer from '../components/Footer.svelte';
	import Header from '../components/Header.svelte';
	import '../styles/globals.css';

	export const ssr = false;
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" />
	<link
		href="https://fonts.googleapis.com/css2?family=Patrick+Hand&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<div class="container mx-auto xl:px-36 min-[300px]:px-5 py-8">
	<Header />
	<slot />
	<Footer />
</div>
