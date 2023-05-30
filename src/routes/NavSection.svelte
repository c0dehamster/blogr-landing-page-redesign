<script lang="ts">
	import Fa from "svelte-fa"
	import { faChevronDown } from "@fortawesome/free-solid-svg-icons"
	import { slide } from "svelte/transition"

	export let label: string
	export let list: Array<string>

	let expanded = false

	const toggleDropdown = () => (expanded = !expanded)
</script>

<div class="section">
	<button class="section__button" on:click={toggleDropdown}>
		{label}

		<span class="section__icon">
			<Fa icon={faChevronDown} />
		</span>
	</button>

	{#if expanded}
		<ul class="section__dropdown" transition:slide={{ duration: 200 }}>
			{#if list.length > 0}
				{#each list as item}
					<li class="section__list-item">
						<a href="#0" class="link">{item}</a>
					</li>
				{/each}
			{/if}
		</ul>
	{/if}
</div>

<style>
	.section {
		width: 100%;
		display: grid;
		justify-items: center;

		border-bottom: 1px solid var(--color-neutral-400);
	}

	.section__button {
		position: relative;
		padding-block-end: 0.5rem;
		padding-inline-end: 2rem;

		background: transparent;
		border: none;

		color: var(--color-neutral-400);

		text-transform: capitalize;
	}

	.section__icon {
		position: absolute;
		right: 0;
		margin-block: auto;
	}

	.section__dropdown {
		padding: 1.5rem;
		width: 100%;

		display: grid;
		justify-items: center;
		gap: 2rem;

		border-top: 1px solid var(--color-neutral-400);
	}

	.link {
		color: var(--color-neutral-400);
	}

	@media screen and (min-width: 60rem) {
		.section {
			border: none;
		}

		.section__button {
			padding-block: 0;
		}

		.section__dropdown {
			position: absolute;
			z-index: 10;
			top: 4rem;

			width: fit-content;

			border: 1px solid var(--color-neutral-400);
			background-color: var(--color-neutral-900);
			opacity: 98%;
			box-shadow: 0.5rem 0.5rem 1rem 0.5rem var(--color-shadow-500);
		}
	}
</style>
