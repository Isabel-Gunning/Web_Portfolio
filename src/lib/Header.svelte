<header class="header">
	<svg class="desktop-wave" viewBox="0 0 1440 220" preserveAspectRatio="xMidYMid slice" aria-hidden="true">
		<path
			d="M0,0 H1440 V135 C1350,135 1320,80 1230,80 C1140,80 1110,135 1020,135 C930,135 900,80 810,80 C720,80 690,135 600,135 C510,135 480,80 390,80 C300,80 270,135 180,135 C90,135 60,110 0,100 Z"
			fill="#f9e983"
		/>
	</svg>

	<svg class="mobile-wave" viewBox="0 0 390 160" preserveAspectRatio="xMidYMid slice" aria-hidden="true">
		<path
			d="M0,0 H390 V95 C325,145 260,45 195,95 C130,145 65,45 0,95 Z"
			fill="#f9e983"
		/>
	</svg>
</header>

<style>
	.header {
		width: 100%;
		height: 240px;
		position: relative;
		overflow: hidden;
	}

	svg {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

	.mobile-wave {
		display: none;
	}

	@media (max-width: 700px) {
		.header {
			height: 160px;
		}

		.desktop-wave {
			display: none;
		}

		.mobile-wave {
			display: block;
		}
	}
</style>