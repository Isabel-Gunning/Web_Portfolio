<script>
	import { base } from "$app/paths";
	import ProjectGalleryPage from "$lib/components/ProjectGalleryPage.svelte";

	const animationItems = [
		{ type: "video", src: `${base}/videos/animation/animation-1.mp4`, alt: "Walk cycle animation of a girl in a blue dress" },
		{ type: "video", src: `${base}/videos/animation/animation-2.mp4`, alt: "Head turn animation of a girl with a butterfly hair clip" },
		{ type: "video", src: `${base}/videos/animation/animation-3.mp4`, alt: "Fire animation" },
		{ type: "video", src: `${base}/videos/animation/animation-4.mp4`, alt: "Water animation" },
		{ type: "video", src: `${base}/videos/animation/animation-5.mp4`, alt: "Bouncing ball animation" },
		{ type: "video", src: `${base}/videos/animation/animation-6.mp4`, alt: "Hand drawn flip book animation of a candle" },
		{ type: "video", src: `${base}/videos/animation/animation-7.mp4`, alt: "Walk cycle animation of a girl with a frog cloak walking through a puddle" },
		{ type: "video", src: `${base}/videos/animation/animation-8.mp4`, alt: "Traffic light animation" },

		{ type: "video", src: `${base}/videos/animation/animation-9.mp4`, alt: "Pixel art animation of a boy in striped pj's with a flash light", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-10.mp4`, alt: "Pixel art animation of a boy in striped pj's jumping", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-11.mp4`, alt: "Pixel art animation of a boy in striped pj's idle", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-12.mp4`, alt: "Pixel art animation of a boy in striped pj's running left", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-13.mp4`, alt: "Pixel art animation of a boy in striped pj's running right", pixel: true },
		{ type: "video", src: `${base}/videos/animation/animation-14.mp4`, alt: "Pixel art animation of a shadow monster spewing blood and broken toys hanging out of its body", pixel: true }
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