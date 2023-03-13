<script>
	// @ts-nocheck

	export let show;
    export let search;
</script>

<form action="/search">
	<input
		type="text"
		class={`rounded-md w-full py-2 px-4 mb-3 bg-[#1F2937] outline-none text-white text-opacity-60 ${
			!show && 'hidden'
		}`}
		placeholder="Search"
		name="q"
		bind:value={search}
	/>
</form>
