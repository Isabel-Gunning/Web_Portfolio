<script>
	import { base } from "$app/paths";
	import ProjectGalleryPage from "$lib/components/ProjectGalleryPage.svelte";

	const modelItems = [
		{ src: `${base}/images/3d/model-1.jpg`, alt: "3D cave in a rock render" },
		{ src: `${base}/images/3d/model-2.jpg`, alt: "3D grass, lake and mountains render" },
		{ src: `${base}/images/3d/model-3.jpg`, alt: "3D rock prop render" },
		{ src: `${base}/images/3d/model-4.jpg`, alt: "3D bus prop render" },
		{ src: `${base}/images/3d/model-5.jpg`, alt: "3D plain mug render" },
		{ src: `${base}/images/3d/model-6.jpg`, alt: "3D scaffold render" },
		{ src: `${base}/images/3d/model-7.jpg`, alt: "3D right hand render" },
		{ src: `${base}/images/3d/model-8.jpg`, alt: "3D book render" },
		{ src: `${base}/images/3d/model-9.jpg`, alt: "3D car/crane render" },
		{ src: `${base}/images/3d/model-10.jpg`, alt: "3D castle on grass render" }
	];
</script>

<ProjectGalleryPage
	title="3D Modelling Projects"
	description="A collection of 3D environment and prop renders I created while learning modelling, lighting, and rendering."
	items={modelItems}
    columns={2}
	ctaText="Check out my Instagram to see more of my work!"
	ctaLink="https://www.instagram.com/izzybizzy477/"
/>