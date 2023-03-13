<script>
// @ts-nocheck

	let menu = [
		{
			slug: 'ui-design',
			name: 'UI Design'
		},
		{
			slug: 'frontend',
			name: 'Front-end'
		},
		{
			slug: 'backend',
			name: 'Back-end'
		},
		{
			slug: 'golang',
			name: 'Golang'
		},
		{
			slug: 'android',
			name: 'Android Developer'
		}
	];

    export let openSidebar;
</script>

<div class={`bg-[#4B5563] fixed top-0 left-0 h-screen w-2/3 px-8 pt-12 z-10 space-y-5 md:hidden ${openSidebar ? 'translate-x-0' : '-translate-x-[500px]'} transition-all ease-in duration-300`}>
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<div class="flex gap-3 justify-end" on:click={() => openSidebar = false}>
		<div class="bg-[#1F2937] bg-opacity-60 w-fit px-2 py-1 rounded-md">
			<span class="text-2xl">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					fill="none"
					viewBox="0 0 24 24"
					stroke-width="2.5"
					stroke="currentColor"
					class="w-6 h-6"
				>
					<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
				</svg>
			</span>
		</div>
	</div>
	{#each menu as { slug, name }}
		<a href="/category/{slug}" class="text-white block p-2 hover:translate-x-6 hover:text-opacity-50 transition-all ease-in duration-200"
			>{name}</a
		>
	{/each}
</div>
