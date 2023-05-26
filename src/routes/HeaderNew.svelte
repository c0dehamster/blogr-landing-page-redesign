<script lang="ts">
	import Fa from "svelte-fa"
	import { faChevronDown } from "@fortawesome/free-solid-svg-icons"

	import iconHamburger from "../lib/images/icon-hamburger.svg"
	import iconClose from "../lib/images/icon-close.svg"
	import logo from "../lib/images/logo.svg"

	let expanded = false

	$: icon = !expanded ? iconHamburger : iconClose
	$: headerContentsClass = `header__contents ${
		expanded ? "header__contents--expanded" : ""
	}`
</script>

<header class="header">
	<button class="toggle-menu">
		<!-- Helper div to create a border on a clipped element -->
		<div class="toggle-menu__contents">
			<span class="sr-only">Menu</span>
			<img src={icon} alt="" class="toggle-menu__icon" />
		</div>
	</button>

	<div class="menu">
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

					<ul class="nav__dropdown">
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
			<button class="button button--outline">Sign Up</button>
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

		padding-inline: var(--padding-main-responsive);

		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.toggle-menu {
		display: none;
	}

	.menu {
		flex: 1;

		display: flex;
		justify-content: space-between;
		align-items: start;
	}

	/* Navigation */

	.nav {
		padding-inline: 2px;
		padding-block-end: 1.5px;

		clip-path: polygon(0 0, 100% 0, 95% 100%, 5% 100%);

		background-color: var(--color-neutral-400);
	}

	.nav__contents {
		height: 2.5rem;

		padding-inline: 2rem;

		clip-path: polygon(0 0, 100% 0, 95% 100%, 5% 100%);

		display: flex;
		align-items: center;
		gap: 2rem;

		background-color: var(--color-neutral-900);
	}

	.nav__dropdown {
		display: none;
	}

	.nav__button {
		background: transparent;
		border: none;

		gap: 0.5rem;

		cursor: pointer;

		color: var(--color-neutral-400);
	}

	/* Account */

	.account {
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 2rem;
	}

	/* Logo */

	.logo {
		width: 76px;
		height: 30px;

		margin-inline-start: 2rem;
	}
</style>
