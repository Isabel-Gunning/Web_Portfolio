<script>
    import Header from "$lib/Header.svelte";
    import Navigation from "$lib/Navigation.svelte";
</script>

<Header />

<Navigation />

<main>
    <section id="about">
        <h1> About Me </h1>
    </section>

    <section id="tech">
        <h1>Technologies / Software</h1>
    </section>

    <section id="projects">
        <h1>Projects</h1>
    </section>
</main>

<style>
    :global(html) {
        scroll-behavior: smooth;
    }

    main {
        padding-top: 300px;
    }

    section {
        min-height: 100vh;
        padding: 2rem;
        scroll-margin-top: 8rem;
    }
</style>