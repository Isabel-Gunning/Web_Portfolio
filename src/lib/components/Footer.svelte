<footer class="footer">
	<p>© 2026 Isabel Gunning. All rights reserved.</p>
</footer>

<style>

	.footer {
		width: 100%;
		padding: var(--space-lg);
		background: var(--color-primary);
		color: var(--color-text-primary);

		display: flex;
		justify-content: center;
		align-items: center;

		text-align: center;
	}

	.footer p {
		margin: 0;
		font-size: var(--font-base);
	}

	@media (max-width: 800px) {
		.footer {
			padding: var(--space-md);
		}

		.footer p {
			font-size: var(--font-sm);
		}
	}
</style>