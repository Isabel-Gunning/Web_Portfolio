<script>
    import Header from "$lib/components/Header.svelte";
    import Navigation from "$lib/components/Navigation.svelte";
    import Footer from "$lib/components/Footer.svelte";
	import ScrollToTop from "$lib/components/ScrollToTop.svelte";

</script>

<Header />
<Navigation />

<main>
    <slot />
</main>

<Footer />
<ScrollToTop />

<style>
    main {
        padding-top: var(--main-padding-top);
    }

   @media (max-width: 800px) {
        main {
            padding-top: var(--main-padding-top-mobile);
        }
   }

</style>