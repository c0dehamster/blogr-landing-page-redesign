<script>
	import "./style.css"

	import HeaderNew from "./HeaderNew.svelte"
	import Footer from "./Footer.svelte"
</script>

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
