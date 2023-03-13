<script>
	import { page } from '$app/stores';
	import PostWrapper from '../../components/Home/PostWrapper.svelte';
	import ResultSearch from '../../components/Search/ResultSearch.svelte';
	let search = $page.url.searchParams.get('q');
</script>

<svelte:head>
	<title>Search: {search ?? ''}</title>
</svelte:head>

<ResultSearch search={search} />

{#if search == 'UI Design'}
	<PostWrapper />
{:else}
	<div class="flex flex-col items-center text-center">
		<h1 class="text-[64px]">No result 😢</h1>
		<p class="text-xl w-1/3">We couldn't find any posts with the keyword `{search}`. Please try another keyword.</p>
	</div>
{/if}
