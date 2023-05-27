<script lang="ts">
	import illustration from "../lib/images/Illustration.png"

	import CardList from "./CardList.svelte"
	import CallToAction from "./CallToAction.svelte"
</script>

<main class="main">
	<section class="hero-screen">
		<h1 class="heading">A modern publishing platform</h1>

		<div class="hero">
			<div class="hero__contents-wrapper">
				<div class="hero__contents">
					<p class="hero__description">
						Grow your audience and build your online brand
					</p>

					<button class="button button--solid">Start for Free</button>
					<button class="button button--outline">Learn More</button>
				</div>
			</div>

			<img src={illustration} alt="" class="hero__image" />
		</div>
	</section>

	<CardList />
	<CallToAction />
</main>

<style>
	.hero-screen {
		padding-block: 7rem;
		padding-inline: var(--padding-main-responsive);

		display: grid;
		gap: 4rem;
		justify-items: center;

		background: linear-gradient(
			45deg,
			var(--color-neutral-900) 40%,
			var(--color-neutral-700)
		);
	}

	.heading {
		color: var(--color-neutral-100);

		font-size: var(--font-size-700);
		text-align: center;
	}

	.hero {
		display: grid;
		gap: 4rem;
	}

	.hero__contents-wrapper {
		justify-self: center;
	}

	.hero__contents {
		display: grid;
		gap: 1.5rem;
		grid-template-areas:
			"description description"
			"start-for-free learn-more";
	}

	.hero__description {
		max-width: 20rem;

		grid-area: description;
		justify-self: center;

		color: var(--color-neutral-100);

		text-align: center;
		font-size: var(--font-size-400);
	}

	.hero__image {
		width: 100%;
		max-width: 35rem;
	}

	@media screen and (min-width: 40rem) {
		.hero {
			/* Overlap content with grid */

			grid-template-rows: repeat(7, 1fr);
			grid-template-columns: repeat(6, 1fr);
			gap: 0px;
		}

		.hero__contents-wrapper,
		.hero__image {
			grid-row: 4 / 5;
		}

		.hero__contents-wrapper {
			width: 100%;

			padding-inline: 3.5rem;
			padding-block: 10% 15%;

			grid-row: 1 / 5;
			grid-column: 1 / 6;

			border: 2px solid var(--color-neutral-400);
		}

		.hero__contents {
			gap: 2.5rem;
		}

		.hero__image {
			grid-column: 2/ -1;
			grid-row: 4 / -1;
		}

		.hero__description {
			font-size: var(--font-size-500);
		}
	}
</style>
