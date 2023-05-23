<section class="services">
	<div class="services__divider">
		<h2 class="services__heading">Designed for the future</h2>
	</div>

	<div class="line" />

	<ul class="services__list">
		<li class="services__list-item">
			<div class="card">
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

		<li class="services__list-item">
			<div class="card">
				<h3 class="card__heading">Robust content management</h3>
				<p class="card__description">
					Flexible content management enables users to easily move
					through posts. Increase the usability of your blog by adding
					customized categories, sections, format, or flow. With this
					functionality, you’re in full control.
				</p>
			</div>
		</li>

		<li class="services__list-item">
			<div class="card">
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

		<li class="services__list-item">
			<div class="card">
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
	}

	.services__divider {
		padding-inline: var(--padding-main-responsive);
		height: 4.5rem;
		display: grid;
		place-items: center;
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
</style>
