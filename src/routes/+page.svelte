<script lang="ts">
	import illustration from "../lib/images/Illustration.png"

	import CardList from "./CardList.svelte"
	import CallToAction from "./CallToAction.svelte"
</script>

<main class="main">
	<section class="hero-screen">
		<h1 class="heading">A modern publishing platform</h1>

		<div class="hero">
			<div class="hero__contents">
				<p class="hero__description">
					Grow your audience and build your online brand
				</p>

				<button class="button button--solid">Start for Free</button>
				<button class="button button--outline">Learn More</button>
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
	}

	.heading {
		font-size: var(--font-size-700);
		text-align: center;
	}

	.hero {
		display: grid;
		gap: 4rem;
	}

	.hero__contents {
		max-width: 25rem;
		justify-self: center;
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

		text-align: center;
		font-size: var(--font-size-400);
	}
</style>
