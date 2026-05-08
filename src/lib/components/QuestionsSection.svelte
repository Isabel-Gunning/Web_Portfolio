<section id="qa" class="qa-section">

    <div class="qa-content">
        <h1>Questions & Answers</h1>

        <p>
            Questions & Answers will go here!
        </p>
    </div>

</section>

<style>
    .qa-section {
        min-height: var(--section-min-height);
        padding: var(--space-xl);
        scroll-margin-top: var(--space-section);

        display: flex;
        align-items: center;
        justify-content: center;
    }

    .qa-content {
        width: 100%;
        max-width: 1100px;
    }

    @media (max-width: 800px) {

        .qa-section {
            padding:
                var(--space-xl)
                var(--space-md);
        }

        .qa-content {
            text-align: center;
        }
    }
</style>