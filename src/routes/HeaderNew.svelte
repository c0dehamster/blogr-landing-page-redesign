<script lang="ts">
	import iconHamburger from "../lib/images/icon-hamburger.svg"
	import iconClose from "../lib/images/icon-close.svg"
	import logo from "../lib/images/logo.svg"

	import NavSection from "./NavSection.svelte"

	let menuExpanded = false

	$: icon = !menuExpanded ? iconHamburger : iconClose
	$: menuClass = `menu ${menuExpanded ? "menu--expanded" : ""}`
</script>

<header class="header">
	<button class="toggle-menu" on:click={() => (menuExpanded = !menuExpanded)}>
		<!-- Helper div to create a border on a clipped element -->
		<div class="toggle-menu__clipped-border" />

		<span class="sr-only">Menu</span>
		<img src={icon} alt="" class="toggle-menu__icon" />
	</button>

	<div class={menuClass}>
		<nav class="nav">
			<!-- Dummy div to avoid clipping of the dropdowns -->
			<div class="nav__clipped-border" />

			<NavSection
				label="product"
				list={[
					"Overview",
					"Pricing",
					"Marketplace",
					"Features",
					"Integrations",
				]} />

			<NavSection
				label="company"
				list={["About", "Team", "Blog", "Careers"]} />

			<NavSection
				label="connect"
				list={["Contact", "Newsletter", "LinkedIn"]} />
		</nav>

		<div class="account">
			<button class="button button--naked">Login</button>

			<button class="button button--outline button--clip-path">
				<span class="button__clipped-border" />

				Sign Up
			</button>
		</div>
	</div>

	<img src={logo} alt="" class="logo" />
</header>

<style>
	/* Let's try desktop first */

	.header {
		position: absolute;
		top: 0;
		z-index: 1;
		width: 100%;

		padding-inline-end: var(--padding-main-responsive);

		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.menu {
		display: none;

		flex: 1;
		max-width: 25rem;
		padding-block: 2.5rem;
		padding-inline: 2rem;

		position: absolute;
		inset-inline: 1.5rem;
		top: 4.5rem;

		gap: 4rem;
		flex-direction: column;
		justify-content: space-between;

		background-color: var(--color-neutral-900);
		opacity: 98%;
		border: 2px solid var(--color-neutral-400);
		box-shadow: 0.5rem 1rem 1.5rem 1rem var(--color-shadow-500);
	}

	.menu--expanded {
		display: flex;
	}

	/* Utilities to simulate non-square borders */

	.nav__clipped-border,
	.button__clipped-border,
	.toggle-menu__clipped-border {
		position: absolute;
		inset: 0;
		z-index: -1;

		clip-path: var(--clip-path);

		background-color: var(--color-neutral-400);
	}

	.nav__clipped-border,
	.button__clipped-border {
		display: none;
	}

	.nav__clipped-border::before,
	.button__clipped-border::before,
	.toggle-menu__clipped-border::before {
		content: "";
		position: absolute;
		clip-path: var(--clip-path);
	}

	.nav__clipped-border::before {
		inset: 0 2px 1.5px 2px;
		background-color: var(--color-neutral-900);
	}

	.button__clipped-border::before {
		inset: 0 2px 1.5px 2px;
		background-color: var(--color-neutral-800);
	}

	.toggle-menu__clipped-border::before {
		inset: 0 2px 1.5px 0;
		background-color: var(--color-neutral-900);
	}

	/* Navigation */

	.nav {
		--clip-path: polygon(0 0, 100% 0, 95% 100%, 5% 100%);

		padding-inline: 2rem;

		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 3rem;
	}

	/* Account */

	.account {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		row-gap: 2rem;
	}

	.button {
		padding-inline: 2.5rem;

		font-size: var(--font-size-400);
	}

	.button--clip-path {
		--clip-path: polygon(0 0, 100% 0, 87.5% 100%, 12.5% 100%);

		background: transparent;
	}

	/* Logo */

	.logo {
		width: 50px;
		height: 20px;

		margin-inline-start: 2rem;
	}

	/* Menu button */

	.toggle-menu {
		position: relative;

		height: 2rem;
		width: 4.5rem;

		--clip-path: polygon(0 0, 100% 0, 80% 100%, 0 100%);
		padding-inline-start: 0.75rem;

		border: none;
		background: transparent;
	}

	@media screen and (min-width: 60rem) {
		.header {
			padding-inline-start: var(--padding-main-responsive);
		}

		.toggle-menu {
			display: none;
		}

		.menu {
			display: flex;
			max-width: 100%;
			padding: 0;

			position: relative;
			inset: auto;

			flex: 1;
			flex-direction: row;
			align-items: start;

			border: none;
			background: transparent;

			box-shadow: none;
		}

		.logo {
			width: 76px;
			height: 30px;
		}

		/* Navigation */

		.nav {
			position: relative;
			height: 2.5rem;
			padding-inline: 2rem;
			gap: 2rem;

			flex-direction: row;
		}

		/* Account */

		.account {
			flex-direction: row;
		}

		.button--clip-path {
			border: none;
		}

		.button__clipped-border,
		.nav__clipped-border {
			display: block;
		}
	}
</style>
