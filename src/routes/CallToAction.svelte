<section class="call-to-action">
	<h2 class="call-to-action__heading">State of the Art Infrastructure</h2>
	<p class="call-to-action__description">
		With reliability and speed in mind, worldwide data centers provide the
		backbone for ultra-fast connectivity. This ensures your site will load
		instantly, no matter where your readers are, keeping your site
		competitive.
	</p>
	<button class="button button--solid">Start for Free</button>
</section>

<style>
	.call-to-action {
		padding-inline: var(--padding-main-responsive);

		display: grid;
		grid-template-areas:
			"heading"
			"description"
			"button";
		gap: 1.5rem;
		justify-items: center;

		text-align: center;
	}

	.call-to-action__heading {
		grid-area: heading;

		font-size: var(--font-size-700);
	}

	.call-to-action__description {
		grid-area: description;
	}

	.button {
		grid-area: button;

		padding-inline: 1.5rem;
	}
</style>
