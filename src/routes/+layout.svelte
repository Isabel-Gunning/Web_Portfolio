<script>
    import Header from "$lib/components/Header.svelte";
    import Navigation from "$lib/components/Navigation.svelte";
    import Footer from "$lib/components/Footer.svelte";

</script>

<Header />
<Navigation />

<main>
    <slot />
</main>

<Footer />

