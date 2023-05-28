<section class="services">
	<div class="services__divider">
		<h2 class="services__heading">Designed for the future</h2>
	</div>

	<div class="line" />

	<ul class="services__list">
		<li class="services__list-item services__list-item--1">
			<div class="card card--1">
				<h3 class="card__heading">Introducing an extensible editor</h3>
				<p class="card__description">
					Blogr features an exceedingly intuitive interface which lets
					you focus on one thing: creating content. The editor
					supports management of multiple blogs and allows easy
					manipulation of embeds such as images, videos, and Markdown.
					Extensibility with plugins and themes provide easy ways to
					add functionality or change the looks of a blog.
				</p>
			</div>
		</li>

		<li class="services__list-item services__list-item--2">
			<div class="card card--2">
				<h3 class="card__heading">Robust content management</h3>
				<p class="card__description">
					Flexible content management enables users to easily move
					through posts. Increase the usability of your blog by adding
					customized categories, sections, format, or flow. With this
					functionality, you’re in full control.
				</p>
			</div>
		</li>

		<li class="services__list-item services__list-item--3">
			<div class="card card--3">
				<h3 class="card__heading">Free, open, simple</h3>
				<p class="card__description">
					Blogr is a free and open source application backed by a
					large community of helpful developers. It supports features
					such as code syntax highlighting, RSS feeds, social media
					integration, third-party commenting tools, and works
					seamlessly with Google Analytics. The architecture is clean
					and is relatively easy to learn.
				</p>
			</div>
		</li>

		<li class="services__list-item services__list-item--4">
			<div class="card card--4">
				<h3 class="card__heading">Powerful tooling</h3>
				<p class="card__description">
					Batteries included. We built a simple and straightforward
					CLI tool that makes customization and deployment a breeze,
					but capable of producing even the most complicated sites.
				</p>
			</div>
		</li>
	</ul>

	<div class="line" />
</section>

<style>
	.services {
		display: grid;

		background: radial-gradient(
			at right,
			var(--color-neutral-700),
			var(--color-neutral-900)
		);
	}

	.services__divider {
		padding-inline: var(--padding-main-responsive);
		height: 4.5rem;
		display: grid;
		place-items: center;

		background-color: var(--color-neutral-600);
		color: var(--color-neutral-100);
	}

	.line {
		width: 60%;
		max-width: 16rem;
		justify-self: center;
		margin-block: 3rem;

		border-bottom: 0.25rem solid var(--color-neutral-400);
	}

	.services__heading {
		font-size: var(--font-size-600);
	}

	.services__list {
		padding-inline: var(--padding-main-responsive);

		display: grid;
		gap: 4rem;
	}

	.card {
		position: relative;

		height: 100%;

		padding-block: 2rem;
		padding-inline: 1.5rem;

		display: grid;
		gap: 1.5rem;

		color: var(--color-neutral-100);
		background-color: var(--color-neutral-600);
	}

	.card__heading {
		font-size: var(--font-size-600);
	}

	@media screen and (min-width: 72rem) {
		.line {
			display: none;
		}

		.services__list {
			padding-block: 9rem;

			grid-template-columns: 1fr 1fr;
			gap: 0;

			--card-offset: 8rem;
			--border-offset: 2rem;
		}

		.services__list-item {
			height: 100%;
		}

		.services__list-item--1 {
			padding-inline-end: var(--card-offset);
			padding-block-end: var(--border-offset);

			justify-items: end;
		}

		.services__list-item--2 {
			padding-block-end: var(--card-offset);
			padding-inline-start: var(--border-offset);
		}

		.services__list-item--3 {
			padding-inline-start: var(--card-offset);
			padding-block-start: var(--border-offset);

			grid-row: 2 / 3;
			grid-column: 2 / -1;
		}

		.services__list-item--4 {
			padding-block-start: var(--card-offset);
			padding-inline-end: var(--border-offset);

			grid-row: 2 / 3;
			grid-column: 1 / 2;
		}

		.card::before {
			content: "";

			position: absolute;
			height: 100%;
			width: 100%;

			/* Temporary */
			--border: 2px solid var(--color-neutral-400);
		}

		.card--1::before {
			top: var(--border-offset);
			left: var(--border-offset);

			border-right: var(--border);
			border-bottom: var(--border);
		}

		.card--2::before {
			top: var(--border-offset);
			right: var(--border-offset);

			border-left: var(--border);
			border-bottom: var(--border);
		}

		.card--3::before {
			bottom: var(--border-offset);
			right: var(--border-offset);

			border-left: var(--border);
			border-top: var(--border);
		}

		.card--4::before {
			bottom: var(--border-offset);
			left: var(--border-offset);

			border-right: var(--border);
			border-top: var(--border);
		}
	}
</style>
