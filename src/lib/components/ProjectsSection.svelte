<section id="projects" class="projects-section">

    <div class="projects-content">
        <h1>Projects</h1>

        <p>
            Projects I've Worked On ...
        </p>
    </div>

</section>

<style>
    .projects-section {
        min-height: var(--section-min-height);
        padding: var(--space-xl);
        scroll-margin-top: var(--space-section);

        display: flex;
        align-items: center;
        justify-content: center;
    }

    .projects-content {
        width: 100%;
        max-width: 1100px;
    }

    @media (max-width: 800px) {

        .projects-section {
            padding:
                var(--space-xl)
                var(--space-md);
        }

        .projects-content {
            text-align: center;
        }
    }
</style>