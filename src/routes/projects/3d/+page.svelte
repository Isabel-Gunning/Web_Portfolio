<script>
	import { base } from "$app/paths";
	import ProjectGalleryPage from "$lib/components/ProjectGalleryPage.svelte";

	const modelItems = [
		{ src: `${base}/images/3d/model-1.jpg`, alt: "3D model render 1" },
		{ src: `${base}/images/3d/model-2.jpg`, alt: "3D model render 2" },
		{ src: `${base}/images/3d/model-3.jpg`, alt: "3D model render 3" },
		{ src: `${base}/images/3d/model-4.jpg`, alt: "3D model render 4" },
		{ src: `${base}/images/3d/model-5.jpg`, alt: "3D model render 5" },
		{ src: `${base}/images/3d/model-6.jpg`, alt: "3D model render 6" },
		{ src: `${base}/images/3d/model-7.jpg`, alt: "3D model render 7" },
		{ src: `${base}/images/3d/model-8.jpg`, alt: "3D model render 8" },
		{ src: `${base}/images/3d/model-9.jpg`, alt: "3D model render 9" },
		{ src: `${base}/images/3d/model-10.jpg`, alt: "3D model render 10" }
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