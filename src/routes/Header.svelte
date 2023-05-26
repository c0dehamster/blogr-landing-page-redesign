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
	<!-- Makeshift border for the clipped button -->
	<div class="header__button-wrapper">
		<button class="header__button">
			<span class="sr-only">Menu</span>
			<img src={icon} alt="" class="icon" />
		</button>
	</div>

	<img src={logo} alt="" class="logo" />

	<div class={headerContentsClass}>
		<nav class="nav">
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
		</nav>

		<div class="account">
			<button class="button button--naked">Login</button>
			<button class="button button--outline">Sign Up</button>
		</div>
	</div>
</header>

<style>
	.header {
		position: absolute;
		top: 0;
		width: 100%;
	}

	.header__contents {
		display: flex;
		align-items: baseline;
		justify-content: space-between;
	}

	.header__button-wrapper {
		display: none;
	}

	.nav {
		display: flex;
		gap: 2.25rem;
	}

	@media screen and (max-width: 40rem) {
		.header__button-wrapper {
			display: block;
			background-color: var(--color-neutral-400);
			position: relative;
			width: 4rem;
			height: 2rem;
			clip-path: polygon(0 0, 100% 0, 80% 100%, 0 100%);
		}

		.header__button {
			display: grid;
			align-items: center;
			padding-left: 0.75rem;

			position: absolute;
			inset: 0.125rem 0.25rem 0.125rem 0.125rem;

			background-color: var(--color-neutral-900);

			clip-path: polygon(0 0, 100% 0, 80% 100%, 0 100%);
			border: none;
		}

		.header__contents {
			/* Temporary */
			display: none;
		}

		.header__contents--expanded {
			display: block;
		}
	}
</style>
