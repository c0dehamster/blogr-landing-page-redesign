<script>
	import logo from "../lib/images/logo.svg"
</script>

<footer class="footer">
	<img src={logo} alt="" class="logo" />

	<nav class="nav">
		<div class="nav__section">
			<h3 class="nav__heading">Product</h3>

			<ul class="nav__list">
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
			<h3 class="nav__heading">Company</h3>

			<ul class="nav__list">
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
			<h3 class="nav__heading">Connect</h3>

			<ul class="nav__list">
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
</footer>

<style>
	.footer {
		padding-block: 4.5rem;
		padding-inline: var(--padding-main-responsive);

		display: grid;
		justify-items: center;
		gap: 4.5rem;

		background-color: var(--color-neutral-900);
	}

	.nav {
		display: grid;
		justify-items: center;
		gap: 2.5rem;

		text-align: center;
		color: var(--color-neutral-400);
	}

	.nav__section {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1rem;
	}

	.nav__list {
		display: grid;
		justify-items: center;
	}

	@media screen and (min-width: 40rem) {
		.nav {
			grid-template-columns: 1fr 1fr 1fr;
		}
	}

	@media screen and (min-width: 72rem) {
		.footer {
			grid-template-columns: 1fr 1fr;
			justify-items: baseline;
		}

		.nav__section {
			align-items: baseline;
			text-align: start;
		}

		.nav__list {
			justify-items: baseline;
			text-align: start;
		}
	}
</style>
