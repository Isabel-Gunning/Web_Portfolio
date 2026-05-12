<script>
	import { base } from "$app/paths";
	import ProjectGalleryPage from "$lib/components/ProjectGalleryPage.svelte";

	const artItems = [
		/* Digital Artwork */
		{ category: "Digital", src: `${base}/images/art/digital-1.png`, alt: "Digital artwork 1" },
		{ category: "Digital", src: `${base}/images/art/digital-2.png`, alt: "Digital artwork 2" },
		{ category: "Digital", src: `${base}/images/art/digital-3.png`, alt: "Digital artwork 3" },
		{ category: "Digital", src: `${base}/images/art/digital-4.png`, alt: "Digital artwork 4" },
		{ category: "Digital", src: `${base}/images/art/digital-5.png`, alt: "Digital artwork 5" },
		{ category: "Digital", src: `${base}/images/art/digital-6.png`, alt: "Digital artwork 6" },
		{ category: "Digital", src: `${base}/images/art/digital-7.png`, alt: "Digital artwork 7" },
		{ category: "Digital", src: `${base}/images/art/digital-8.png`, alt: "Digital artwork 8" },
		{ category: "Digital", src: `${base}/images/art/digital-9.png`, alt: "Digital artwork 9" },
		{ category: "Digital", src: `${base}/images/art/digital-10.png`, alt: "Digital artwork 10" },
		{ category: "Digital", src: `${base}/images/art/digital-11.png`, alt: "Digital artwork 11" },
		{ category: "Digital", src: `${base}/images/art/digital-12.png`, alt: "Digital artwork 12" },
		{ category: "Digital", src: `${base}/images/art/digital-13.png`, alt: "Digital artwork 13" },
		{ category: "Digital", src: `${base}/images/art/digital-14.png`, alt: "Digital artwork 14" },
		{ category: "Digital", src: `${base}/images/art/digital-15.png`, alt: "Digital artwork 15" },
        { category: "Digital", src: `${base}/images/art/digital-16.png`, alt: "Digital artwork 16" },


		/* Traditional Artwork */
		{ category: "Traditional", src: `${base}/images/art/traditional-1.jpg`, alt: "Traditional artwork 1" },
		{ category: "Traditional", src: `${base}/images/art/traditional-2.jpg`, alt: "Traditional artwork 2" },
		{ category: "Traditional", src: `${base}/images/art/traditional-3.jpg`, alt: "Traditional artwork 3" },
		{ category: "Traditional", src: `${base}/images/art/traditional-4.jpg`, alt: "Traditional artwork 4" },
		{ category: "Traditional", src: `${base}/images/art/traditional-5.jpg`, alt: "Traditional artwork 5" },
		{ category: "Traditional", src: `${base}/images/art/traditional-6.jpg`, alt: "Traditional artwork 6" },
		{ category: "Traditional", src: `${base}/images/art/traditional-7.jpg`, alt: "Traditional artwork 7" },
		{ category: "Traditional", src: `${base}/images/art/traditional-8.jpg`, alt: "Traditional artwork 8" },
		{ category: "Traditional", src: `${base}/images/art/traditional-9.jpg`, alt: "Traditional artwork 9" },
		{ category: "Traditional", src: `${base}/images/art/traditional-10.jpg`, alt: "Traditional artwork 10" },
		{ category: "Traditional", src: `${base}/images/art/traditional-11.jpg`, alt: "Traditional artwork 11" }
	];
</script>

<ProjectGalleryPage
	title="Art Projects"
	description="A collection of some of my traditional and digital artwork, including character designs, sketches, and creative experiments."
	items={artItems}
	filters={["Digital", "Traditional"]}
	ctaText="Check out my Instagram to see more of my artwork!"
	ctaLink="https://www.instagram.com/izzybizzy477/"
/>