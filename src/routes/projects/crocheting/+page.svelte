<script>
	import { base } from "$app/paths";
	import ProjectGalleryPage from "$lib/components/ProjectGalleryPage.svelte";

	const crochetItems = [
        { src: `${base}/images/crochet/crochet-1.jpg`, alt: "Crochet project 1" },
        { src: `${base}/images/crochet/crochet-2.jpg`, alt: "Crochet project 2" },
        { src: `${base}/images/crochet/crochet-3.jpg`, alt: "Crochet project 3" },
        { src: `${base}/images/crochet/crochet-4.jpg`, alt: "Crochet project 4" },
        { src: `${base}/images/crochet/crochet-5.jpg`, alt: "Crochet project 5" },
        { src: `${base}/images/crochet/crochet-6.jpg`, alt: "Crochet project 6" }
    ];
</script>

<ProjectGalleryPage
	title="Crochet Projects"
	description="My collection of handmade plushies."
	items={crochetItems}
	columns={3}
/>