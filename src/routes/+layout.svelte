<script>
	import "./style.css"

	import HeaderNew from "./HeaderNew.svelte"
	import Footer from "./Footer.svelte"
</script>

<svelte:head>
	<title>Frontend Mentor | Blogr landing page</title>
</svelte:head>

<div class="app">
	<HeaderNew />
	<slot />
	<Footer />
</div>

<style>
	.app {
		position: relative;
	}
</style>
