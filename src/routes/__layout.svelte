<script>
	import '../app.css';
	import Header from '$lib/components/header.svelte';
	import Footer from '$lib/components/footer.svelte';
</script>

<div class="flex flex-col min-h-screen">
	<Header />
	<main class="container flex-grow my-10">
		<slot />
	</main>
	<Footer />
</div>
