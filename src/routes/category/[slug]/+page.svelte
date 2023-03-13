<script>
	// @ts-nocheck

	import { page } from '$app/stores';
	import PostWrapper from '../../../components/Home/PostWrapper.svelte';
	import ResultSearch from '../../../components/Search/ResultSearch.svelte';
	let slug = $page.params.slug;

	let data = [
		{
			slug: 'ui-design',
			category: 'UI Design'
		},
		{
			slug: 'frontend',
			category: 'Front End'
		},
		{
			slug: 'backend',
			category: 'Back End'
		},
		{
			slug: 'golang',
			category: 'Golang'
		},
		{
			slug: 'android',
			category: 'Android Developer'
		}
	];

	let find_data = Object.values(data).find((ds) => slug == ds.slug)
</script>

<svelte:head>
	<title>Category - {find_data.category}</title>
</svelte:head>

<ResultSearch bind:search={find_data.category} />
<PostWrapper />
