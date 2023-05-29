<script lang="ts">
	import Fa from "svelte-fa"
	import { faChevronDown } from "@fortawesome/free-solid-svg-icons"

	import iconHamburger from "../lib/images/icon-hamburger.svg"
	import iconClose from "../lib/images/icon-close.svg"
	import logo from "../lib/images/logo.svg"

	let expanded = true

	$: icon = !expanded ? iconHamburger : iconClose
	$: menuClass = `menu ${expanded ? "menu--expanded" : ""}`
</script>

<header class="header">
	<button class="toggle-menu">
		<!-- Helper div to create a border on a clipped element -->
		<div class="toggle-menu__contents">
			<span class="sr-only">Menu</span>
			<img src={icon} alt="" class="toggle-menu__icon" />
		</div>
	</button>

	<div class={menuClass}>
		<nav class="nav">
			<div class="nav__contents">
				<div class="nav__section">
					<button class="nav__button">
						Product

						<span class="nav__icon">
							<Fa icon={faChevronDown} />
						</span>
					</button>

					<ul class="nav__dropdown">
						<li class="nav__list-item">
							<a href="#0" class="link">Overview</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">Pricing</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">Marketplace</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">Features</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">Integrations</a>
						</li>
					</ul>
				</div>

				<div class="nav__section">
					<button class="nav__button">
						Company

						<span class="nav__icon">
							<Fa icon={faChevronDown} />
						</span>
					</button>

					<ul class="nav__dropdown nav__dropdown--expanded">
						<li class="nav__list-item">
							<a href="#0" class="link">About</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">Team</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">Blog</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">Careers</a>
						</li>
					</ul>
				</div>

				<div class="nav__section">
					<button class="nav__button">
						Connect

						<span class="nav__icon">
							<Fa icon={faChevronDown} />
						</span>
					</button>

					<ul class="nav__dropdown">
						<li class="nav__list-item">
							<a href="#0" class="link">Contact</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">Newsletter</a>
						</li>

						<li class="nav__list-item">
							<a href="#0" class="link">LinkedIn</a>
						</li>
					</ul>
				</div>
			</div>
		</nav>

		<div class="account">
			<button class="button button--naked">Login</button>

			<div class="button-border">
				<button class="button button--naked button--clip-path">
					Sign Up
				</button>
			</div>
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

		position: fixed;
		inset-inline: 1.5rem;
		top: 4.5rem;

		flex-direction: column;
		justify-content: space-between;

		background-color: var(--color-neutral-900);
		border: 2px solid var(--color-neutral-400);
	}

	.menu--expanded {
		display: flex;
	}

	/* Navigation */

	.nav {
		padding-inline: 2px;
		padding-block-end: 1.5px;

		--clip-path: polygon(0 0, 100% 0, 95% 100%, 5% 100%);
	}

	.nav__contents {
		padding-inline: 2rem;

		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 3rem;

		background-color: var(--color-neutral-900);
	}

	.nav__section {
		width: 100%;
		display: grid;
		justify-items: center;
	}

	.nav__button {
		padding-block-end: 0.5rem;

		background: transparent;
		border: none;

		gap: 0.5rem;

		cursor: pointer;

		color: var(--color-neutral-400);
	}

	.nav__dropdown {
		height: 0;
		width: 100%;
		overflow: hidden;

		display: grid;
		justify-items: center;
		gap: 2rem;

		border-top: 2px solid var(--color-neutral-400);
	}

	.nav__dropdown--expanded {
		padding: 1.5rem;
		height: auto;
		border-bottom: 2px solid var(--color-neutral-400);
	}

	.link {
		color: var(--color-neutral-400);
	}

	/* Account */

	.account {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		gap: 2rem;
	}

	.button-border {
		padding-inline: 2px;
		padding-block-end: 1.5px;

		--clip-path: polygon(0 0, 100% 0, 87.5% 100%, 12.5% 100%);

		border: 2px solid var(--color-neutral-400);
	}

	.button--clip-path {
		padding-inline: 2.5rem;

		background-color: var(--color-neutral-800);
	}

	/* Logo */

	.logo {
		width: 50px;
		height: 20px;

		margin-inline-start: 2rem;
	}

	.toggle-menu {
		display: block;

		padding-block-end: 2px;
		padding-inline-end: 2px;
		--clip-path: polygon(0 0, 100% 0, 80% 100%, 0 100%);
		clip-path: var(--clip-path);

		border: none;

		background-color: var(--color-neutral-400);
	}

	.toggle-menu__contents {
		height: 2rem;
		width: 4.5rem;

		display: grid;
		align-items: center;

		padding-inline-start: 0.75rem;
		clip-path: var(--clip-path);

		background-color: var(--color-neutral-900);
	}

	@media screen and (min-width: 60rem) {
		.header {
			padding-inline-start: var(--padding-main-responsive);
		}

		.toggle-menu {
			display: none;
		}

		.menu {
			max-width: 100%;
			padding: 0;

			position: relative;
			inset: auto;

			flex: 1;
			flex-direction: row;
			align-items: start;

			border: none;
			background: transparent;
		}

		.nav {
			position: relative;
			padding-inline: 2px;
			padding-block-end: 1.5px;

			clip-path: var(--clip-path);

			background-color: var(--color-neutral-400);
		}

		.nav__contents {
			height: 2.5rem;

			padding-inline: 2rem;

			flex-direction: row;

			clip-path: var(--clip-path);

			background-color: var(--color-neutral-900);
		}

		.nav__dropdown--expanded {
			display: grid;
			position: absolute;
			z-index: 10;
			top: 2rem;

			border: 1px solid var(--color-neutral-400);
		}

		.account {
			flex-direction: row;
		}

		.button-border {
			padding-inline: 2px;
			padding-block-end: 1.5px;

			clip-path: var(--clip-path);

			background-color: var(--color-neutral-400);
			border: none;
		}

		.button--clip-path {
			clip-path: var(--clip-path);
		}

		.logo {
			width: 76px;
			height: 30px;

			margin-inline-start: 2rem;
		}
	}
</style>
