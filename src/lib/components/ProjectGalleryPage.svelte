<script>
	import { resolve } from "$app/paths";

	export let title = "";
	export let description = "";

	/** @type {{ src: string, alt: string, category?: string, type?: string, pixel?: boolean }[]} */
	export let items = [];

	/** @type {string[]} */
	export let filters = [];

	export let ctaText = "";
	export let ctaLink = "";
	export let columns = 4;

	let activeFilter = "all";

	$: if (filters.length > 0 && activeFilter === "all") {
		activeFilter = filters[0];
	}

	$: visibleItems =
		filters.length > 0
			? items.filter((item) => item.category === activeFilter)
			: items;

	function openCtaLink() {
		if (ctaLink) {
			window.open(ctaLink, "_blank", "noopener,noreferrer");
		}
	}
</script>

<section class="project-page">
	<div class="project-content">
		<button
			class="back-link"
			on:click={() => window.location.href = resolve("/") + "#projects"}
		>
			← Back to Projects
		</button>

		<div class="project-heading">
			<h1>{title}</h1>
			<p>{description}</p>
		</div>

		{#if filters.length > 0}
			<div class="filter-nav">
				{#each filters as filter (filter)}
					<button
						class:active={activeFilter === filter}
						on:click={() => activeFilter = filter}
					>
						{filter}
					</button>
				{/each}
			</div>
		{/if}

		{#if visibleItems.length > 0}
			<div class="gallery-grid" style={`column-count: ${columns};`}>
				{#each visibleItems as item (item.src)}
					<article class:pixel-card={item.pixel} class="gallery-card">
						{#if item.type === "video"}
							<video
								src={item.src}
								muted
								loop
								playsinline
								preload="metadata"
								on:mouseenter={(event) => event.currentTarget.play()}
								on:mouseleave={(event) => {
									event.currentTarget.pause();
									event.currentTarget.currentTime = 0;
								}}
							>
								<track kind="captions" />
							</video>
						{:else}
							<img src={item.src} alt={item.alt} />
						{/if}
					</article>
				{/each}
			</div>
		{/if}

		{#if ctaText && ctaLink}
			<button class="cta-link" on:click={openCtaLink}>
				{ctaText}
			</button>
		{/if}
	</div>
</section>

<style>
	.project-page {
		min-height: 100vh;
		padding: 0 var(--space-lg) var(--space-xl);
		background: var(--color-background);
	}

	.project-content {
		width: 100%;
		max-width: 1050px;
		margin: 0 auto;
		text-align: center;
	}

	.back-link {
		position: fixed;
		top: 30px;
		left: 30px;
		z-index: 100;
		padding: 0.65rem 1rem;
		border: none;
		border-radius: var(--radius-pill);
		background: var(--project-card-background);
		color: var(--color-text-muted);
		box-shadow: 5px 6px 0 var(--project-card-shadow);
		font-family: var(--font-body);
		font-size: var(--font-base);
		cursor: pointer;
		transition:
			transform var(--transition-fast),
			color var(--transition-fast),
			box-shadow var(--transition-fast),
			background-color var(--transition-fast);
	}

	.back-link:hover {
		transform: translateY(-4px);
		color: var(--color-text-primary);
		box-shadow: 7px 9px 0 var(--project-card-shadow-hover);
	}

	.project-heading {
		max-width: 780px;
		margin: 0 auto 2rem;
	}

	.project-heading h1 {
		margin-bottom: var(--space-md);
		font-size: var(--font-display);
		color: var(--color-text-primary);
	}

	.project-heading p {
		margin: 0 auto;
		font-size: var(--font-lg);
		line-height: 1.6;
		color: var(--color-text-primary);
	}

	.filter-nav {
		width: fit-content;
		margin: 0 auto 2.5rem;
		padding: 0.35rem;
		display: flex;
		gap: 0;
		border-radius: var(--radius-pill);
		background: var(--tech-filter-background);
		box-shadow: 5px 6px 0 var(--project-card-shadow);
	}

	.filter-nav button {
		padding: 0.75rem 1.5rem;
		border: none;
		border-radius: var(--radius-pill);
		background: transparent;
		color: var(--color-text-muted);
		font-family: var(--font-body);
		font-size: var(--font-base);
		cursor: pointer;
		transition:
			transform var(--transition-fast),
			color var(--transition-fast);
	}

	.filter-nav button:hover {
		transform: translateY(-2px);
		color: var(--color-text-primary);
	}

	.filter-nav button.active {
		background: var(--tech-filter-active-background);
		color: var(--tech-filter-active-text);
		box-shadow: 4px 5px 0 var(--project-card-shadow);
	}

	.gallery-grid {
		column-gap: 1.5rem;
	}

	.gallery-card {
		break-inside: avoid;
		margin-bottom: 1.5rem;
		padding: 0.7rem;
		background: var(--project-card-background);
		border: 2px solid var(--project-card-border);
		border-radius: 22px;
		box-shadow: 6px 8px 0 var(--project-card-shadow);
		transition:
			transform var(--transition-fast),
			box-shadow var(--transition-fast);
	}

	.gallery-card:hover {
		transform: translateY(-6px);
		box-shadow: 10px 12px 0 var(--project-card-shadow-hover);
	}

	.gallery-card img,
	.gallery-card video {
		width: 100%;
		height: auto;
		display: block;
		border-radius: 16px;
		background: var(--project-image-background);
	}

	.gallery-card.pixel-card video {
		height: 220px;
		object-fit: contain;
		padding: 0.5rem;
	}

	.cta-link {
		margin-top: var(--space-xl);
		padding: 0.85rem 1.5rem;
		border: none;
		border-radius: var(--radius-pill);
		background: var(--color-primary);
		color: var(--color-text-primary);
		font-family: var(--font-body);
		font-size: var(--font-base);
		cursor: pointer;
		box-shadow: 5px 6px 0 var(--project-card-shadow);
		transition:
			transform var(--transition-fast),
			background-color var(--transition-fast),
			box-shadow var(--transition-fast);
	}

	.cta-link:hover {
		transform: translateY(-4px);
		background: var(--color-primary);
		box-shadow: 7px 9px 0 var(--project-card-shadow-hover);
	}

	@media (max-width: 1000px) {
		.gallery-grid {
			column-count: 3 !important;
		}
	}

	@media (max-width: 800px) {
		.project-page {
			padding: 0 var(--space-md) var(--space-xl);
		}

		.back-link {
			position: static;
			margin-bottom: var(--space-lg);
		}

		.project-heading {
			padding-top: 0;
			margin-bottom: var(--space-lg);
		}

		.project-heading h1 {
			font-size: 2.7rem;
		}

		.project-heading p {
			font-size: var(--font-base);
		}

		.filter-nav {
			width: 100%;
			max-width: 320px;
			margin-bottom: var(--space-lg);
		}

		.filter-nav button {
			flex: 1;
			padding: 0.7rem 0.8rem;
		}

		.gallery-grid {
			column-count: 2 !important;
			column-gap: 1rem;
		}

		.gallery-card {
			margin-bottom: 1rem;
			padding: 0.5rem;
			border-radius: 16px;
		}

		.gallery-card.pixel-card video {
			height: 180px;
		}
	}
</style>