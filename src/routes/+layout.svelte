<script>
	import "./style.css"

	import Header from "./Header.svelte"
	import Footer from "./Footer.svelte"
</script>

<div class="app">
	<Header />
	<slot />
	<Footer />
</div>

<style>
	.app {
		position: relative;
	}
</style>
