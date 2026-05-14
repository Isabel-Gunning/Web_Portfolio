<script>
	import { base } from "$app/paths";
	import { onMount } from "svelte";

	const profileImage = `${base}/images/pictures/Isabel_Gunning.jpg`;

	let showMore = false;

	const roles = [
		"an Artist",
		"an Animator",
		"a 3D Modeller",
		"a UI/UX Designer",
		"an Interactive Designer",
		"a Concept Designer",
		"a Creative Coder",
		"a World Builder"
	];

	let roleIndex = 0;
	let typedRole = "";
	let isDeleting = false;

	onMount(() => {
		let charIndex = 0;

		const typeInterval = setInterval(() => {
			const currentRole = roles[roleIndex];

			if (!isDeleting) {
				typedRole = currentRole.slice(0, charIndex + 1);
				charIndex++;

				if (charIndex === currentRole.length) {
					setTimeout(() => {
                        isDeleting = true;
                    },  900);
				}
			} else {
				typedRole = currentRole.slice(0, charIndex - 1);
				charIndex--;

				if (charIndex === 0) {
					isDeleting = false;
					roleIndex = (roleIndex + 1) % roles.length;
				}
			}
		}, isDeleting ? 120 : 180);

		return () => clearInterval(typeInterval);
	});
</script>

<section id="about" class="about-section">
	<div class="about-content">

		<div class="about-text">
			<p class="intro-label">Welcome to my portfolio</p>

			<h1>
				Hello, I'm <span>Isabel</span>
			</h1>

			<h2>
				I'm <span class="animated-role">{typedRole}</span><span class="cursor">|</span>
			</h2>

			<p>
				I have a huge passion for all things art and animation and I create to build worlds that didn't exist before.
			</p>

			{#if showMore}
				<p id="about-more-text">
					My journey began with a childhood curiosity for design, which has since evolved into a passion for creating unique, weird and wonderful characters through art and animation.
					Creativity is my ultimate escape and my greatest freedom.
					My goal is simple, to translate the amazement and peace I find in the creative process into visual experiences that spark that same joy for others!
				</p>
			{/if}

			<button
				type="button"
				class="read-more-button"
				aria-expanded={showMore}
				aria-controls="about-more-text"
				on:click={() => showMore = !showMore}
			>
				{showMore ? "Read less" : "Read more"}
			</button>
		</div>

		<div class="profile-polaroid">
			<div class="polaroid-tape"></div>

			<img
				src={profileImage}
				alt="Portrait of Isabel Gunning"
			/>

			<p>Isabel Gunning</p>
		</div>

	</div>
</section>

<style>
	.about-section {
		min-height: auto;
		padding: 20px var(--space-lg) var(--space-xl);
		scroll-margin-top: 220px;
		display: flex;
		justify-content: center;
	}

	.about-content {
		width: 100%;
		max-width: 1100px;
		display: grid;
		grid-template-columns: minmax(0, 1fr) 330px;
		align-items: start;
		gap: var(--space-xl);
	}

	.about-text {
		max-width: 820px;
	}

	.intro-label {
		margin-bottom: var(--space-sm);
		font-size: var(--font-base);
		letter-spacing: 0.08em;
		text-transform: uppercase;
		color: var(--color-text-muted);
		font-weight: bold;
	}

	.about-text h1 {
		margin-bottom: var(--space-sm);
		font-size: clamp(2.4rem, 4.4vw, 4rem);
		line-height: 1;
		color: var(--color-text-primary);
	}

	.about-text h1 span {
		color: var(--color-text-primary);
	}

	.about-text h2 {
		min-height: 3.5rem;
		margin-bottom: var(--space-lg);
		font-family: var(--font-heading);
		font-size: clamp(2rem, 4vw, 3.2rem);
		color: var(--color-text-primary);
	}

	.animated-role {
		display: inline-block;
		color: var(--tech-pin-background);
	}

	.cursor {
		color: var(--tech-pin-background);
		animation: blink 0.8s infinite;
	}

	.about-text p {
		font-size: var(--font-lg);
		line-height: 1.8;
	}

	.profile-polaroid {
		position: relative;
		width: 100%;
		max-width: 300px;
		justify-self: center;
		margin-top: 0.1rem;
		padding: 1rem 1rem 1.3rem;
		background: var(--project-card-background);
		border: 2px solid var(--project-card-border);
		border-radius: 22px;
		box-shadow: 10px 12px 0 var(--project-card-shadow);
		transform: rotate(2deg);
		text-align: center;
	}

	.polaroid-tape {
		position: absolute;
		top: -18px;
		left: 50%;
		width: 80px;
		height: 30px;
		background: var(--tech-pin-background);
		border-radius: 6px;
		transform: translateX(-50%) rotate(-4deg);
		box-shadow: 3px 3px 0 var(--project-tape-shadow);
	}

	.profile-polaroid img {
		width: 100%;
		height: 300px;
		object-fit: cover;
		object-position: center;
		border-radius: 16px;
		background: var(--project-image-background);
	}

	.profile-polaroid p {
		margin: 1rem 0 0;
		font-size: var(--font-lg);
		color: var(--color-text-primary);
	}

	.read-more-button {
		margin-top: var(--space-md);
		padding: 0.8rem 1.4rem;
		border: none;
		border-radius: var(--radius-pill);
		background: var(--color-primary);
		color: var(--color-text-primary);
		font-family: var(--font-body);
		font-size: var(--font-base);
		cursor: pointer;
		transition: transform var(--transition-fast);
	}

	.read-more-button:hover {
		transform: scale(var(--scale-hover));
	}

	@keyframes blink {
		0%, 50% {
			opacity: 1;
		}

		51%, 100% {
			opacity: 0;
		}
	}

	@media (max-width: 1000px) {
		.about-section {
			padding: 15px var(--space-md) var(--space-xl);
			overflow-x: hidden;
		}

		.about-content {
			grid-template-columns: 1fr;
			text-align: center;
			gap: var(--space-lg);
		}

		.about-text {
			max-width: 340px;
			justify-self: center;
		}

		.about-text h1 {
			font-size: 3.2rem;
		}

		.about-text h2 {
			font-size: 2.2rem;
		}

		.about-text p {
			font-size: var(--font-base);
			line-height: 1.7;
		}

		.profile-polaroid {
			max-width: 250px;
			order: -1;
			margin-top: 0;
		}

		.profile-polaroid img {
			height: 250px;
		}
	}
</style>