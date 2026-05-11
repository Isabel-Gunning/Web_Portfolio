<script>
	import { base } from "$app/paths";
</script>

<section id="contact" class="contact-section">

	<div class="contact-content">

		<h1>Contact Me</h1>

		<p>
			Feel free to reach out through any of the links below. I'm always happy to connect with others, chat about creative projects, and explore new opportunities!
		</p>

		<div class="contact-grid">

			<!-- Instagram Account-->
			<div class="contact-card">

				<div class="icon-wrapper">
					<a
						href="https://www.instagram.com/izzybizzy477/"
						target="_blank"
						rel="noopener noreferrer"
					>
						<img
							src={`${base}/images/icons/instagram.svg`}
							alt="Instagram icon"
							class="contact-icon"
						/>
					</a>
				</div>

				<h2>Instagram</h2>

				<a
					href="https://www.instagram.com/izzybizzy477/"
					target="_blank"
					rel="noopener noreferrer"
				>
					@izzybizzy477
				</a>

			</div>

			<!-- Email Address-->
			<div class="contact-card">

				<div class="icon-wrapper">
					<a href="mailto:isabel.faye.gunning@gmail.com">
						<img
							src={`${base}/images/icons/gmail.svg`}
							alt="Gmail icon"
							class="contact-icon"
						/>
					</a>
				</div>

				<h2>Gmail</h2>

				<a href="mailto:isabel.faye.gunning@gmail.com">
					isabel.faye.gunning@gmail.com
				</a>

			</div>

			<!-- Phone Number-->
			<div class="contact-card">

				<div class="icon-wrapper">
					<img
						src={`${base}/images/icons/phone.svg`}
						alt="Phone icon"
						class="contact-icon"
					/>
				</div>

				<h2>Phone</h2>

				<p>
					+353 083 460 8469
				</p>

			</div>

		</div>

	</div>

</section>


<style>

	.contact-section {
		min-height: var(--section-min-height);
		padding:
            10px
			var(--space-xl)
			var(--space-lg);

		scroll-margin-top: 50px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.contact-content {
		width: 100%;
		max-width: 1100px;
		text-align: center;
	}

	.contact-content h1 {
		margin-bottom: var(--space-md);
	}

	.contact-content > p {
		margin-bottom: 3rem;
		font-size: var(--font-lg);
		line-height: 1.7;
	}

	.contact-grid {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 1.5rem;
	}

	.contact-card {
		width: 230px;
		padding:
			1.6rem
			1rem;

		background-color: #f8d7e3;
		border-radius: 24px;
		box-shadow: 10px 12px 0 rgba(85, 49, 27, 0.10);
		text-align: center;
		transition:
			transform var(--transition-fast),
			box-shadow var(--transition-fast);
	}

	.contact-card:hover {
		transform: translateY(-6px);
		box-shadow: 14px 16px 0 rgba(85, 49, 27, 0.12);
	}

	.icon-wrapper {
		display: flex;
		justify-content: center;
		margin-bottom: 1rem;
	}

	.contact-icon {
		width: 52px;
		height: 52px;
		object-fit: contain;
		transition:
			transform var(--transition-fast),
			opacity var(--transition-fast);
	}

	.icon-wrapper a:hover .contact-icon {
		transform: scale(1.08);
		opacity: 0.85;
	}

	.contact-card h2 {
		margin-bottom: 0.7rem;
		font-family: var(--font-heading);
		font-size: 1.5rem;
		color: var(--color-text-primary);
	}

	.contact-card a,
	.contact-card p {
		font-family: var(--font-body);
		font-size: var(--font-base);
		color: #8a4d67;
		text-decoration: none;
		word-break: break-word;
		transition: color var(--transition-fast);
	}

	.contact-card a:hover {
		color: #b05f83;
	}

	@media (max-width: 800px) {

		.contact-section {
			padding:
				var(--space-xl)
				var(--space-md);
		}

		.contact-content > p {
			font-size: var(--font-base);
		}

		.contact-card {
			width: 100%;
			max-width: 280px;
		}
	}

</style>