<script>
	import { base } from "$app/paths";
	import ProjectGalleryPage from "$lib/components/ProjectGalleryPage.svelte";

	const crochetItems = [
        { src: `${base}/images/crochet/crochet-1.jpg`, alt: "Crochet bee plushie" },
        { src: `${base}/images/crochet/crochet-2.jpg`, alt: "Crochet jellyfish plushie" },
        { src: `${base}/images/crochet/crochet-3.jpg`, alt: "Crochet snom plushie" },
            { src: `${base}/images/crochet/crochet-4.jpg`, alt: "Large crochet axolotl plushie" },
        { src: `${base}/images/crochet/crochet-5.jpg`, alt: "Crochet shark plushie" },
        { src: `${base}/images/crochet/crochet-6.jpg`, alt: "Crochet dinosaurs" }
    ];
</script>

<ProjectGalleryPage
	title="Crochet Projects"
	description="My collection of handmade plushies."
	items={crochetItems}
	columns={3}
/>