<script>
	import SearchBarMobile from "./Search/SearchBarMobile.svelte";

	let title = 'Epictetus';
	let search = '';

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

	let isOpen = false;
	function toggleMenu() {
		return (isOpen = !isOpen);
	}

	let openSearchMobile = false;
	function toggleSearchMobile() {
		return (openSearchMobile = !openSearchMobile)
	}
</script>

<div class="flex justify-between items-center md:pb-12 min-[300px]:pb-6">
	<div class="md:hidden min-[300px]:block">
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke-width="2"
			stroke="currentColor"
			class="w-6 h-6 text-white text-opacity-50"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
			/>
		</svg>
	</div>

	<div class="flex gap-3 items-center">
		<div class="bg-[#4B5563] w-fit px-4 py-1 rounded-md drop-shadow-lg">
			<span class="text-2xl">{title.charAt(0)}</span>
		</div>
		<h1 class="text-lg">
			<a href="/">{title}</a>
		</h1>
	</div>

	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<div class="md:hidden min-[300px]:block" on:click={() => toggleSearchMobile()}>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke-width="2.5"
			stroke="currentColor"
			class="w-6 h-w-6 text-white text-opacity-50"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"
			/>
		</svg>
	</div>

	<div class="space-x-5 md:block min-[300px]:hidden">
		{#if menu.length > 3}
			{#each menu.splice(0, 3) as { slug, name }}
				<a href={`/category/${slug}`}>{name}</a>
			{/each}
			<div class="inline-block relative">
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<div class="inline-flex gap-2 place-items-center" on:click={() => toggleMenu()}>
					<!-- svelte-ignore a11y-invalid-attribute -->
					<a data-sveltekit-preload-data="tap" href="#">Lainnya</a>
					{#if isOpen}
						<svg
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="2.5"
							stroke="currentColor"
							class="w-4 h-4"
						>
							<path stroke-linecap="round" stroke-linejoin="round" d="M4.5 15.75l7.5-7.5 7.5 7.5" />
						</svg>
					{:else}
						<svg
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="2.5"
							stroke="currentColor"
							class="w-4 h-4"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M19.5 8.25l-7.5 7.5-7.5-7.5"
							/>
						</svg>
					{/if}
				</div>
				<div
					class={`absolute top-8 -left-7 w-36 px-4 py-2 bg-[#283140] rounded-md text-white text-opacity-60 ${
						isOpen ? 'opacity-100' : 'opacity-0'
					} transition-all ease-in-out duration-100`}
				>
					{#each menu as { slug, name }}
						<a href={`/category/${slug}`} class="block py-1">{name}</a>
					{/each}
				</div>
			</div>
		{:else}
			{#each menu as { slug, name }}
				<a href={`/category/${slug}`}>{name}</a>
			{/each}
		{/if}
	</div>

	<div class="relative md:block min-[300px]:hidden">
		<span class="absolute top-3 left-4">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="w-4 h-w-4 text-white text-opacity-50"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"
				/>
			</svg>
		</span>
		<form action="/search">
			<input
				type="text"
				class="bg-[#1F2937] bg-opacity-60 rounded-full outline-none pr-8 pl-12 py-2"
				placeholder="Search"
				name="q"
				bind:value={search}
			/>
		</form>
	</div>
</div>
<SearchBarMobile show={openSearchMobile} search={search} />