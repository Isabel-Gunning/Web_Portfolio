<script>
	import { base } from "$app/paths";
	import ProjectGalleryPage from "$lib/components/ProjectGalleryPage.svelte";

	const animationItems = [
		{ type: "video", src: `${base}/videos/animation/animation-1.mp4`, alt: "Animation project 1" },
		{ type: "video", src: `${base}/videos/animation/animation-2.mp4`, alt: "Animation project 2" },
		{ type: "video", src: `${base}/videos/animation/animation-3.mp4`, alt: "Animation project 3" },
		{ type: "video", src: `${base}/videos/animation/animation-4.mp4`, alt: "Animation project 4" },
		{ type: "video", src: `${base}/videos/animation/animation-5.mp4`, alt: "Animation project 5" },
		{ type: "video", src: `${base}/videos/animation/animation-6.mp4`, alt: "Animation project 6" },
		{ type: "video", src: `${base}/videos/animation/animation-7.mp4`, alt: "Animation project 7" },
		{ type: "video", src: `${base}/videos/animation/animation-8.mp4`, alt: "Animation project 8" },

		{ type: "video", src: `${base}/videos/animation/animation-9.mp4`, alt: "Pixel animation 1", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-10.mp4`, alt: "Pixel animation 2", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-11.mp4`, alt: "Pixel animation 3", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-12.mp4`, alt: "Pixel animation 4", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-13.mp4`, alt: "Pixel animation 5", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-14.mp4`, alt: "Pixel animation 6", pixel: true }
	];
</script>

<ProjectGalleryPage
	title="Animation Projects"
	description="A collection of short hand-drawn, pixel art, and digitally designed animations."
	items={animationItems}
	columns={3}
	ctaText="Check out my Instagram to see more of my work!"
	ctaLink="https://www.instagram.com/izzybizzy477/"
/>