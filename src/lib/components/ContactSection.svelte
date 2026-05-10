<section id="contact" class="contact-section">

    <div class="contact-content">
        <h1>Contact Me</h1>

        <p>
            Contact me through ...
        </p>
    </div>

</section>

<style>
    .contact-section {
        min-height: var(--section-min-height);
        padding: var(--space-xl);
        scroll-margin-top: var(--space-section);

        display: flex;
        align-items: center;
        justify-content: center;
    }

    .contact-content {
        width: 100%;
        max-width: 1100px;
    }

    @media (max-width: 800px) {

        .contact-section {
            padding:
                var(--space-xl)
                var(--space-md);
        }

        .contact-content {
            text-align: center;
        }
    }
</style>