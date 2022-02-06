<script>
	let links = [
		{ name: 'Home', url: '/' },
		{ name: 'Academics', url: '/blog' },
		{ name: 'Honors', url: '/honors' },
		{ name: 'Resume', url: '/resume' },
		{ name: 'Reflections', url: '/reflections' }
	];
</script>

<header class="flex items-center justify-between py-6 font-bold container border-b">
	<a href="/" class="hover:opacity-60 transition-all">
		<img src="/logo.svg" alt="Logo" />
	</a>
	<nav>
		{#each links as link}
			<a href={link.url} class="transition-all p-3 opacity-60 hover:opacity-100">{link.name}</a>
		{/each}
	</nav>
	<a
		href="contact"
		class="flex items-center bg-amber-100 text-amber-900 hover:translate-x-1 hover:bg-amber-900 hover:text-amber-100 transition-all px-4 py-2 rounded-full"
		><span>Contact me</span>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			class="h-6 w-6 -mr-2"
			viewBox="0 0 20 20"
			fill="currentColor"
		>
			<path
				fill-rule="evenodd"
				d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
				clip-rule="evenodd"
			/>
		</svg></a
	>
</header>
