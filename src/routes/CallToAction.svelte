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
		padding-block: 4.5rem;
		padding-inline: var(--padding-main-responsive);

		display: grid;
		grid-template-areas:
			"heading"
			"description"
			"button";
		gap: 2rem;
		justify-items: center;

		background-color: var(--color-neutral-600);

		text-align: center;
	}

	.call-to-action__heading {
		grid-area: heading;

		color: var(--color-neutral-100);

		font-size: var(--font-size-700);
	}

	.call-to-action__description {
		max-width: 36rem;
		grid-area: description;

		color: var(--color-neutral-100);
	}

	.button {
		grid-area: button;

		padding-inline: 1.5rem;
	}

	@media screen and (min-width: 72rem) {
		.call-to-action {
			grid-template-areas:
				"heading description"
				"button description";
			row-gap: 0;
			column-gap: 4rem;
		}

		.call-to-action__heading {
			align-self: baseline;
			justify-self: baseline;

			text-align: start;
		}

		.button {
			align-self: flex-end;
			justify-self: start;
		}

		.call-to-action__description {
			justify-self: end;
			height: 100%;
			padding-block-start: 0.5rem;
			text-align: end;
		}
	}
</style>
