<script> 
    import {base} from "$app/paths";

    const projectCategories = [
        {
            name:"Art",
            image: `${base}/images/pictures/art.png`,
            link: "/projects/art"
        },
        {
            name:"Animation",
            image: `${base}/images/pictures/animation.jpg`,
            link: "/projects/animation"
        },
        {
            name:"Coding",
            image: `${base}/images/pictures/coding.png`,
            link: "/projects/coding"
        },
        {
            name:"3D Modelling",
            image: `${base}/images/pictures/3d.png`,
            link: "/projects/3d"
        },
        {
            name:"Crocheting",
            image: `${base}/images/pictures/crocheting.jpg`,
            link: "/projects/crocheting"
        }
    ];
</script>

<section id="projects" class="projects-section">

    <div class="projects-content">
        <h1>Projects I've Worked On</h1>

        <p>
            A collection of projects I've worked on across different creative mediums. Click a polaroid below to explore each project category!
        </p>

        <div class="project-grid">
            {#each projectCategories as category (category.name)}

            	<!-- eslint-disable-next-line svelte/no-navigation-without-resolve -->
                <a href={category.link} class="project-polaroid">

					<div class="polaroid-tape"></div>

					<div class="polaroid-image">
						<img src={category.image} alt={category.name} />
					</div>

					<div class="polaroid-caption">
						<h2>{category.name}</h2>
					</div>

				</a>
            {/each}
        </div>
    </div>

</section>

<style>
    .projects-section {
        min-height: var(--section-min-height);
        padding: 
            3rem
            var(--space-xl)
            var(--space-xl);

        scroll-margin-top: 70px;
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
            5.5rem;

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
		background-color: #fffaf0;
		border: 2px solid rgba(85, 49, 27, 0.08);
		border-radius: 18px;
		padding:
			0.9rem
			0.9rem
			1.2rem;

		text-decoration: none;
		color: var(--color-text-primary);
		box-shadow: 10px 12px 0 rgba(85, 49, 27, 0.12);
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
        box-shadow: 14px 18px 0 rgba(85, 49, 27, 0.14);
    }

    .polaroid-tape {
		position: absolute;
		top: -18px;
		left: 50%;
		width: 72px;
		height: 28px;
		background-color: #aed5ee;
		border-radius: 6px;
		transform: translateX(-50%) rotate(-3deg);
		box-shadow: 3px 3px 0 rgba(85, 49, 27, 0.08);
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
		background-color: #f4f4f4;
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
            padding:
                var(--space-xl)
                var(--space-md);
        }

        .projects-content p {
            margin-bottom: 4rem;
        }

         .project-grid {
            grid-template-columns: repeat(2, 1fr);
            gap: var(--space-xl);
        }

        .project-polaroid {
			max-width: 165px;
			padding:
				0.8rem
				0.8rem
				1rem;
		}

		.polaroid-image {
			height: 125px;
		}

		.polaroid-caption h2 {
			font-size: var(--font-base);
		}
    }
</style>