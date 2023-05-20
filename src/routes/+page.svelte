<script>
	import illustration from "../lib/images/Illustration.png"
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

	<section class="services">
		<div class="services__divider">
			<h2 class="services__heading">Designed for the future</h2>
		</div>

		<ul class="services__list">
			<li class="services__list-item">
				<div class="card">
					<h3 class="card__heading">
						Introducing an extensible editor
					</h3>
					<p class="card__description">
						Blogr features an exceedingly intuitive interface which
						lets you focus on one thing: creating content. The
						editor supports management of multiple blogs and allows
						easy manipulation of embeds such as images, videos, and
						Markdown. Extensibility with plugins and themes provide
						easy ways to add functionality or change the looks of a
						blog.
					</p>
				</div>
			</li>

			<li class="services__list-item">
				<div class="card">
					<h3 class="card__heading">Robust content management</h3>
					<p class="card__description">
						Flexible content management enables users to easily move
						through posts. Increase the usability of your blog by
						adding customized categories, sections, format, or flow.
						With this functionality, you’re in full control.
					</p>
				</div>
			</li>

			<li class="services__list-item">
				<div class="card">
					<h3 class="card__heading">Free, open, simple</h3>
					<p class="card__description">
						Blogr is a free and open source application backed by a
						large community of helpful developers. It supports
						features such as code syntax highlighting, RSS feeds,
						social media integration, third-party commenting tools,
						and works seamlessly with Google Analytics. The
						architecture is clean and is relatively easy to learn.
					</p>
				</div>
			</li>

			<li class="services__list-item">
				<div class="card">
					<h3 class="card__heading">Powerful tooling</h3>
					<p class="card__description">
						Batteries included. We built a simple and
						straightforward CLI tool that makes customization and
						deployment a breeze, but capable of producing even the
						most complicated sites.
					</p>
				</div>
			</li>
		</ul>
	</section>
</main>
