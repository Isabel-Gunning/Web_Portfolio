<script>
	import { base } from "$app/paths";
	import { onMount } from "svelte";

	let active = "about";

	function goToSection(id = "about") {
		active = id;
		window.location.href = `${base}/#${id}`;
	}

	onMount(() => {
		const sectionIds = ["about", "tech", "projects", "qa", "contact"];

		const handleScroll = () => {
			for (const id of sectionIds) {
				const el = document.getElementById(id);

				if (!el) continue;

				const rect = el.getBoundingClientRect();

				if (rect.top <= 350 && rect.bottom >= 350) {
					active = id;
				}
			}
		};

		window.addEventListener("scroll", handleScroll);
		handleScroll();

		return () => {
			window.removeEventListener("scroll", handleScroll);
		};
	});
</script>

<nav class="section-nav" aria-label="Section navigation">
	<button
		type="button"
		class:active={active === "about"}
		aria-current={active === "about" ? "page" : undefined}
		on:click={() => goToSection("about")}
	>
		<img src={`${base}/images/icons/profile.svg`} alt="" />
		<span>About</span>
	</button>

	<button
		type="button"
		class:active={active === "tech"}
		aria-current={active === "tech" ? "page" : undefined}
		on:click={() => goToSection("tech")}
	>
		<img src={`${base}/images/icons/tech.svg`} alt="" />
		<span>Tech</span>
	</button>

	<button
		type="button"
		class:active={active === "projects"}
		aria-current={active === "projects" ? "page" : undefined}
		on:click={() => goToSection("projects")}
	>
		<img src={`${base}/images/icons/projects.svg`} alt="" />
		<span>Projects</span>
	</button>

	<button
		type="button"
		class:active={active === "qa"}
		aria-current={active === "qa" ? "page" : undefined}
		on:click={() => goToSection("qa")}
	>
		<img src={`${base}/images/icons/questions.svg`} alt="" />
		<span>Q&A</span>
	</button>

	<button
		type="button"
		class:active={active === "contact"}
		aria-current={active === "contact" ? "page" : undefined}
		on:click={() => goToSection("contact")}
	>
		<img src={`${base}/images/icons/contact.svg`} alt="" />
		<span>Contact</span>
	</button>
</nav>

<style>
	.section-nav {
		position: sticky;
		top: 12px;
		z-index: 100;
		margin: 0 auto;
		width: 520px;
		padding: 0.35rem;
		border-radius: var(--radius-pill);
		background: rgba(255, 255, 255, 0.85);
		display: flex;
		align-items: center;
		justify-content: space-between;
		box-shadow: 0 8px 24px rgba(0, 0, 0, 0.08);
		backdrop-filter: blur(8px);
	}

	.section-nav button {
		flex: 1;
		padding: 0.8rem 1rem;
		border: none;
		border-radius: var(--radius-pill);
		background: transparent;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 0.5rem;
		color: var(--color-text-muted);
		font-family: var(--font-body);
		font-size: var(--font-base);
		cursor: pointer;
		transition:
			background-color var(--transition-fast),
			color var(--transition-fast),
			transform var(--transition-fast);
	}

	.section-nav img {
		width: 26px;
		height: 26px;
		object-fit: contain;
		opacity: 0.65;
	}

	.section-nav button:hover {
		transform: translateY(-2px);
	}

	.section-nav button.active {
		background: var(--color-primary);
		color: var(--color-text-primary);
		box-shadow: 0 4px 14px rgba(0, 0, 0, 0.08);
	}

	.section-nav button.active img {
		opacity: 1;
	}

	@media (max-width: 650px) {
		.section-nav {
			width: 90%;
			padding: 0.4rem;
		}

		.section-nav button {
			padding: 0.7rem 0.4rem;
			gap: 0;
		}

		.section-nav button span {
			display: none;
		}

		.section-nav img {
			width: 24px;
			height: 24px;
		}
	}
</style>