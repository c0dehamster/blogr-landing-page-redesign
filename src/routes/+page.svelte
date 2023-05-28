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

		font-size: clamp(var(--font-size-700), 5vw, var(--font-size-900));
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

	.button--solid {
		grid-area: start-for-free;
		box-shadow: 0.2rem 0.1rem 1rem 0.5rem var(--color-shadow-500);
	}

	.button--outline {
		grid-area: learn-more;
		box-shadow: 0.2rem 0.1rem 1rem 0.5rem var(--color-shadow-500);
	}

	.hero__image {
		width: 100%;
		max-width: 35rem;

		box-shadow: 1rem 1rem 2rem 0.5rem var(--color-shadow-500);
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
			box-shadow: 1rem 1rem 2rem 0.5rem var(--color-shadow-500);
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

	@media screen and (min-width: 72rem) {
		.hero-screen {
			min-height: min(100vh, 62.5rem);
		}

		.hero {
			grid-template-columns: repeat(5, 1fr);
			grid-template-rows: 1fr 1fr 1fr;
		}

		.hero__contents-wrapper {
			grid-row: 1 / 3;
			grid-column: 1 / 4;

			padding-inline-end: 40%;
			padding-block: 3.5rem;

			align-items: center;
		}

		.hero__image {
			max-width: auto;

			grid-row: 2 / 4;
			grid-column: 3 / 7;
		}

		.hero__contents {
			grid-template-columns: 1fr 1fr 1fr;
			grid-template-areas:
				"description description description"
				"start-for-free start-for-free ."
				". learn-more learn-more";
		}

		.hero__description {
			text-align: start;
		}
	}
</style>
