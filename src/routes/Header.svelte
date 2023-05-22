<script lang="ts">
	import Fa from "svelte-fa"
	import { faChevronDown } from "@fortawesome/free-solid-svg-icons"

	import iconHamburger from "../lib/images/icon-hamburger.svg"
	import iconClose from "../lib/images/icon-close.svg"

	let expanded = false

	$: icon = !expanded ? iconHamburger : iconClose
</script>

<header class="header">
	<button class="header__button">
		<span class="sr-only">Menu</span>
		<img src={icon} alt="" class="icon" />
	</button>

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
					<a href="0#" class="link">Overview</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">Pricing</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">Marketplace</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">Features</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">Integrations</a>
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
					<a href="0#" class="link">About</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">Team</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">Blog</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">Careers</a>
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
					<a href="0#" class="link">Contact</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">Newsletter</a>
				</li>

				<li class="nav__list-item">
					<a href="0#" class="link">LinkedIn</a>
				</li>
			</ul>
		</div>
	</nav>

	<div class="account">
		<button class="button button--naked">Login</button>
		<button class="button button--outline">Sign Up</button>
	</div>
</header>

<style>
	.header {
		position: absolute;
		top: 0;
		width: 100%;

		display: flex;
		align-items: baseline;
		justify-content: space-between;
	}

	.header__button {
		display: none;
	}

	.nav {
		display: flex;
		gap: 2.25rem;
	}
</style>
