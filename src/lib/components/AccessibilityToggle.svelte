<script>
	import { base } from "$app/paths";
	import { onMount } from "svelte";

	let highContrast = false;

	const darkModeOffIcon = `${base}/images/icons/dark_mode_off.svg`;
	const darkModeOnIcon = `${base}/images/icons/dark_mode_on.svg`;

	onMount(() => {
		highContrast = localStorage.getItem("highContrast") === "true";
		document.body.classList.toggle("high-contrast", highContrast);
	});

	function toggleHighContrast() {
		highContrast = !highContrast;

		document.body.classList.toggle("high-contrast", highContrast);
		localStorage.setItem("highContrast", String(highContrast));
	}
</script>

<button
	class="accessibility-toggle"
	on:click={toggleHighContrast}
	aria-label={highContrast ? "Switch to light mode" : "Switch to dark mode"}
	title={highContrast ? "Switch to light mode" : "Switch to dark mode"}
>
	<img
		src={highContrast ? darkModeOnIcon : darkModeOffIcon}
		alt=""
	/>
</button>

<style>
	.accessibility-toggle {
		position: fixed;
		bottom: 24px;
		left: 24px;
		width: 56px;
		height: 42px;
		border-radius: var(--radius-pill);
		background: var(--floating-button-background);
		backdrop-filter: blur(6px);
		border: none;
		cursor: pointer;
		display: flex;
		align-items: center;
		justify-content: center;
		z-index: 999;
		box-shadow: 0 4px 12px var(--floating-button-shadow);
		transition:
			transform var(--transition-fast),
			background-color var(--transition-fast),
			opacity var(--transition-fast);
			
	}

	.accessibility-toggle:hover {
		transform: scale(var(--scale-hover));
		background: var(--floating-button-background-hover);
	}

	.accessibility-toggle img {
		width: 28px;
		height: 28px;
		object-fit: contain;
	}

	@media (max-width: 800px) {
		.accessibility-toggle {
			width: 50px;
			height: 38px;
			bottom: 18px;
			left: 18px;
		}

		.accessibility-toggle img {
			width: 24px;
			height: 24px;
		}
	}

</style>