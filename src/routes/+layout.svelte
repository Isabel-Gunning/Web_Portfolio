<script>
    import Header from "$lib/components/Header.svelte";
    import Navigation from "$lib/components/Navigation.svelte";
    import Footer from "$lib/components/Footer.svelte";
	import ScrollToTop from "$lib/components/ScrollToTop.svelte";
    import AccessibilityToggle from "$lib/components/AccessibilityToggle.svelte";

</script>

<a href="#main-content" class="skip-link">
	Skip to main content
</a>

<AccessibilityToggle />
<Header />
<Navigation />

<main id="main-content">
    <slot />
</main>

<Footer />
<ScrollToTop />

<style>
    .skip-link {
        position: absolute;
        top: -40px;
        left: 20px;
        background: var(--color-primary);
        color: var(--color-text-primary);
        padding: 0.8rem 1rem;
        border-radius: var(--radius-md);
        z-index: 1000;
        transition: top 0.2s ease;
    }

    .skip-link:focus {
        top: 20px;
    }

    main {
        padding-top: var(--main-padding-top);
    }

   @media (max-width: 800px) {
        main {
            padding-top: var(--main-padding-top-mobile);
        }
   }
</style>