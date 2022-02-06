<script>
	let links = [
		{ name: 'Home', url: '/' },
		{ name: 'Academics', url: '/blog' },
		{ name: 'Honors', url: '/honors' },
		{ name: 'Resume', url: '/resume' },
		{ name: 'Reflections', url: '/reflections' }
	];

	let navOpen = false;

	function handleNav() {
		navOpen = !navOpen;
	}
</script>

<header class="flex flex-wrap items-center justify-between py-6 font-bold container border-b">
	<a href="/" class="flex h-10 hover:opacity-60 transition-all">
		<img src="/logo.svg" alt="Logo" />
	</a>
	<div class="flex md:order-2">
		<a
			href="contact"
			class="flex items-center bg-amber-100 text-amber-900 md:hover:translate-x-1 hover:bg-amber-900 hover:text-amber-100 transition-all px-4 py-2 rounded-full"
			><span>Contact me</span>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6 -mr-2 hidden md:block"
				viewBox="0 0 20 20"
				fill="currentColor"
			>
				<path
					fill-rule="evenodd"
					d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
					clip-rule="evenodd"
				/>
			</svg>
		</a>
		<button on:click={handleNav}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-10 p-1 ml-4 hover:opacity-60 md:hidden"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
			>
				<path
					class:hidden={navOpen}
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16M4 18h16"
				/>
				<path
					class:hidden={!navOpen}
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M6 18L18 6M6 6l12 12"
				/>
			</svg>
		</button>
	</div>
	<nav
		class="md:flex flex flex-col md:flex-row w-full md:w-auto mt-6 md:mt-0"
		class:hidden={!navOpen}
	>
		{#each links as link}
			<a
				href={link.url}
				class="transition-all text-4xl py-4 md:p-3 md:text-base opacity-60 hover:opacity-100"
				>{link.name}</a
			>
		{/each}
	</nav>
</header>
