<script>
	import { base, resolve } from "$app/paths";
</script>

<section id="projects" class="projects-section">

	<div class="projects-content">
		<h1>Projects I've Worked On</h1>

		<p>
			A collection of projects I've worked on across different creative mediums.
			Click a polaroid below to explore each project category!
		</p>

		<div class="project-grid">

			<a href={resolve("/projects/art")} class="project-polaroid">
				<div class="polaroid-tape"></div>

				<div class="polaroid-image">
					<img
						src={`${base}/images/pictures/art.png`}
						alt="Art project preview"
					/>
				</div>

				<div class="polaroid-caption">
					<h2>Art</h2>
				</div>
			</a>

			<a href={resolve("/projects/animation")} class="project-polaroid">
				<div class="polaroid-tape"></div>

				<div class="polaroid-image">
					<img
						src={`${base}/images/pictures/animation.jpg`}
						alt="Animation project preview"
					/>
				</div>

				<div class="polaroid-caption">
					<h2>Animation</h2>
				</div>
			</a>

			<a href={resolve("/projects/coding")} class="project-polaroid">
				<div class="polaroid-tape"></div>

				<div class="polaroid-image">
					<img
						src={`${base}/images/pictures/coding.png`}
						alt="Coding project preview"
					/>
				</div>

				<div class="polaroid-caption">
					<h2>Coding</h2>
				</div>
			</a>

			<a href={resolve("/projects/3d")} class="project-polaroid">
				<div class="polaroid-tape"></div>

				<div class="polaroid-image">
					<img
						src={`${base}/images/pictures/3d.png`}
						alt="3D modelling project preview"
					/>
				</div>

				<div class="polaroid-caption">
					<h2>3D Modelling</h2>
				</div>
			</a>

			<a href={resolve("/projects/crocheting")} class="project-polaroid">
				<div class="polaroid-tape"></div>

				<div class="polaroid-image">
					<img
						src={`${base}/images/pictures/crocheting.jpg`}
						alt="Crocheting project preview"
					/>
				</div>

				<div class="polaroid-caption">
					<h2>Crocheting</h2>
				</div>
			</a>

		</div>
	</div>

</section>

<style>
    .projects-section {
        min-height: var(--section-min-height);
        padding-top: 10px;
	    padding-inline: var(--space-lg);
	    padding-bottom: var(--space-xl);
        scroll-margin-top: 90px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .projects-content {
        width: 100%;
        max-width: 1100px;
        text-align:center;
    }

    .projects-content h1 {
        margin-bottom: var(--space-md);
    }

    .projects-content p {
        max-width: 900px;
        margin: 
            0 auto
            4rem;

        font-size: var(--font-lg);
        line-height: 1.7;
    }

    .project-grid {
        width: 100%;
        display: grid;
        grid-template-columns: 
            repeat(auto-fit, minmax(180px, 1fr));

        gap: 3.5rem 3rem;
        justify-items: center;
        align-items: start;
    }

    .project-polaroid {
		position: relative;
		width: 100%;
		max-width: 190px;
		background-color: var(--project-card-background);
		border: 2px solid var(--project-card-border);
		border-radius: 18px;
		padding:
			0.9rem
			0.9rem
			1.2rem;

		text-decoration: none;
		color: var(--color-text-primary);
		box-shadow: 10px 12px 0 var(--project-card-shadow);
		transform: rotate(-1.5deg);
		transition:
			transform var(--transition-fast),
			box-shadow var(--transition-fast);
	}

    .project-polaroid:nth-child(even) {
        transform: rotate(1.5deg);
    }

    .project-polaroid:hover {
        transform: rotate(0deg) translateY(-8px);
        box-shadow: 14px 18px 0 var(--project-card-shadow-hover);
    }

    .polaroid-tape {
		position: absolute;
		top: -18px;
		left: 50%;
		width: 72px;
		height: 28px;
		background-color: var(--project-tape-background);
		border-radius: 6px;
		transform: translateX(-50%) rotate(-3deg);
		box-shadow: 3px 3px 0 var(--project-tape-shadow);
	}

    .project-polaroid:nth-child(even) 
    .polaroid-tape {
		transform: translateX(-50%) rotate(3deg);
	}

	.polaroid-image {
		height: 160px;
		border-radius: 14px;
		overflow: hidden;
		margin-bottom: 1rem;
		background-color: var(--project-image-background);
	}

    .polaroid-image img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		display: block;
	}

	.polaroid-caption h2 {
		margin: 0;
		font-family: var(--font-body);
		font-size: var(--font-lg);
		color: var(--color-text-primary);
	}

    @media (max-width: 800px) {

        .projects-section {
            padding: 90px var(--space-xl) var(--space-md);
            scroll-margin-top: 110px;
        }

        .projects-content p {
            margin-bottom: 4rem;
        }

         .project-grid {
            grid-template-columns: repeat(2, 1fr);
            gap: var(--space-xl);
        }

        .project-polaroid {
			max-width: 145px;
			padding:
				0.65rem
				0.65rem
				0.80rem;
		}

		.polaroid-image {
			height: 80px;
            margin-bottom: 0.2rem;
		}

		.polaroid-caption h2 {
			font-size: var(--font-base);
            line-height: 1.2;
		}
    }
</style>