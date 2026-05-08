<script>
    import AboutSection from "$lib/components/AboutSection.svelte";
	import ProjectsSection from "$lib/components/ProjectsSection.svelte";
	import QuestionsSection from "$lib/components/QuestionsSection.svelte";
	import TechSection from "$lib/components/TechSection.svelte";
</script>

<main>
    <AboutSection/>
    <TechSection/>
    <ProjectsSection/>
    <QuestionsSection />
</main>

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