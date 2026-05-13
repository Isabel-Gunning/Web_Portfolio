<script>
	import { base } from "$app/paths";
	import ProjectGalleryPage from "$lib/components/ProjectGalleryPage.svelte";

	const artItems = [
		/* Digital Artwork */
		{ category: "Digital", src: `${base}/images/art/digital-1.png`, alt: "Girl crouched poster" },
		{ category: "Digital", src: `${base}/images/art/digital-2.png`, alt: "Animal crossing character" },
		{ category: "Digital", src: `${base}/images/art/digital-3.png`, alt: "Girl with a gun" },
		{ category: "Digital", src: `${base}/images/art/digital-4.png`, alt: "Man from the circus" },
		{ category: "Digital", src: `${base}/images/art/digital-5.png`, alt: "Girl with butterfly on her nose" },
		{ category: "Digital", src: `${base}/images/art/digital-6.png`, alt: "Girl crouched original picture" },
		{ category: "Digital", src: `${base}/images/art/digital-7.png`, alt: "Slime ranchers slimes" },
		{ category: "Digital", src: `${base}/images/art/digital-8.png`, alt: "Slime rancher slimes 2" },
		{ category: "Digital", src: `${base}/images/art/digital-9.png`, alt: "Totoro" },
		{ category: "Digital", src: `${base}/images/art/digital-10.png`, alt: "Darth Vader" },
		{ category: "Digital", src: `${base}/images/art/digital-11.png`, alt: "Girl wielding a scythe" },
		{ category: "Digital", src: `${base}/images/art/digital-12.png`, alt: "Noe and Vanitas" },
		{ category: "Digital", src: `${base}/images/art/digital-13.png`, alt: "Character turn around of a girl" },
		{ category: "Digital", src: `${base}/images/art/digital-14.png`, alt: "Capybara with a bee hat" },
		{ category: "Digital", src: `${base}/images/art/digital-15.png`, alt: "Skeleton spider" },
        { category: "Digital", src: `${base}/images/art/digital-16.png`, alt: "Girl in water" },


		/* Traditional Artwork */
		{ category: "Traditional", src: `${base}/images/art/traditional-1.jpg`, alt: "Rengoku" },
		{ category: "Traditional", src: `${base}/images/art/traditional-2.jpg`, alt: "Maomao" },
		{ category: "Traditional", src: `${base}/images/art/traditional-3.jpg`, alt: "Titan-chan" },
		{ category: "Traditional", src: `${base}/images/art/traditional-4.jpg`, alt: "Girl under the autumn leaves" },
		{ category: "Traditional", src: `${base}/images/art/traditional-5.jpg`, alt: "Kiernan" },
		{ category: "Traditional", src: `${base}/images/art/traditional-6.jpg`, alt: "Kiernan 2" },
		{ category: "Traditional", src: `${base}/images/art/traditional-7.jpg`, alt: "Girl portrait" },
		{ category: "Traditional", src: `${base}/images/art/traditional-8.jpg`, alt: "Zoey" },
		{ category: "Traditional", src: `${base}/images/art/traditional-9.jpg`, alt: "Self portrait" },
		{ category: "Traditional", src: `${base}/images/art/traditional-10.jpg`, alt: "Solo leveling God statue" },
		{ category: "Traditional", src: `${base}/images/art/traditional-11.jpg`, alt: "Young girl walking" }
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