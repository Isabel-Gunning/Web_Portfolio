<script> 
    import {base} from "$app/paths";

    const projectCategories = [
        {
            name:"Art",
            icon: `${base}/images/icons/art.svg`,
            link: "/projects/art"
        },
        {
            name:"Animation",
            icon: `${base}/images/icons/animation.svg`,
            link: "/projects/animation"
        },
        {
            name:"Coding",
            icon: `${base}/images/icons/coding.svg`,
            link: "/projects/art"
        },
        {
            name:"3D Modelling",
            icon: `${base}/images/icons/3d.svg`,
            link: "/projects/art"
        },
        {
            name:"Crocheting",
            icon: `${base}/images/icons/crocheting.svg`,
            link: "/projects/crocheting"
        }
    ];
</script>

<section id="projects" class="projects-section">

    <div class="projects-content">
        <h1>Projects I've Worked On</h1>

        <p>
            A collection of projects I've worked on across different creative mediums!
        </p>

        <div class="project-grid">
            {#each projectCategories as category (category.name)}

                <a href={category.link} class="project-folder">

                    <div class="folder-tab">
                        <img src={category.icon} alt={category.name} />
                    </div>

                    <div class="folder-flap"></div>

                    <div class="folder-content">
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

        scroll-margin-top: 40px;
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

    .project-folder {
        position: relative;
        width: 100%;
        max-width: 220px;
        height: 170px;
        text-decoration: none;
        background: #aed5ee;
        border-radius: 18px;
        box-shadow: 10px 12px 0 rgba(85, 49, 27, 0.12);
        transform: rotate(-1.5deg);
        transition: 
            transform var(--transition-fast),
            box-shadow var(--transition-fast);

        display: flex;
        align-items: center;
        justify-content: center;
        overflow: visible;
    }

    .project-folder:nth-child(even) {
        transform: rotate(1.5deg);
    }

    .project-folder:hover {
        transform: rotate(0deg) translateY(-8px);
        box-shadow: 14px 18px 0 rgba(85, 49, 27, 0.14);
    }

    .folder-tab {
        position: absolute;
        top: -24px;
        left: 22px;
        width: 92px;
        height: 48px;
        background: #aed5ee;
        border-radius: 16px 16px 0 0;
        z-index: 3;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .folder-tab img {
        width: 34px;
        height: 34px;
        object-fit: contain;
    }

    .folder-flap {
        position: absolute;
        left: 0;
        bottom: 0;
        width: 100%;
        height: 72%;
        background: #cfe9fb;
        border-radius: 18px;
        transform-origin: bottom center;
        transition: 
            transform var(--transition-fast),
            background-color var(--transition-fast),
            box-shadow var(--transition-fast);
        
        z-index: 1;
        box-shadow: 
            inset 0 3px 0  #cfe9fb,
            inset 0 -14px 22px rgba(91, 139, 170, 0.22);
    }

    .project-folder:hover .folder-flap {
        transform: 
            perspective(700px)
            rotateX(-18deg)
            translateY(8px);
        
        background: #aed1e9;
        box-shadow: 
            inset 0 4px 0 rgba(159, 189, 210, 0.85),
            inset 0 -18px 26px rgba(91, 139, 170, 0.28),
            0 10px 16px rgba(85, 49, 27, 0.08);
    }

    .folder-content {
        position: relative;
        z-index: 2;
        display: flex;
        align-items: center;
        justify-content: center;
        padding-top: 3.5rem;
        transition: transform var(--transition-fast); 
    }

    .project-folder:hover .folder-content {
        transform: translateY(-4px); 
    }

    .folder-content h2 {
        margin: 0;
        color: var(--color-text-primary);
        font-size: 1.5rem;
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

        .project-folder {
            max-width: 180px;
            height: 150px;
        }

        .folder-tab {
            width: 78px;
            height: 42px;
        }

        .folder-tab img {
            width: 28px;
            height: 28px;
        }

        .folder-content h2 {
            font-size: var(--font-lg);
        }
    }
</style>