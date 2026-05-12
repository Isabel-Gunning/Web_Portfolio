<script>
    const questions = [
        {
            question: 'Question here?',
            answer: 'answer to question!'
        },
        {
            question: 'Question here?',
            answer: 'answer to question!'
        },
        {
            question: 'Question here?',
            answer: 'answer to question!'
        },
        {
            question: 'Question here?',
            answer: 'answer to question!'
        },
        {
            question: 'Question here?',
            answer: 'answer to question!'
        },
        {
            question: 'Question here?',
            answer: 'answer to question!'
        }
    ];

</script>

<section id="qa" class="qa-section">

    <div class="qa-content">
        <div class="qa-heading">
            <h1>Questions & Answers</h1>
            <p>A few quick questions about me, my work, and how I create!</p>
        </div>

        <div class="notebook">
            <div class="notebook-page">
                <div class="notebook-line"></div>

                <div class="page-bubbles">
					{#each questions as item, index (index)}
						<div class:qa-pair={true} class:right={index % 2 !== 0}>
							<div class="question-bubble">
								<span>Q</span>
								<p>{item.question}</p>
							</div>

							<div class="answer-bubble">
								<span>A</span>
								<p>{item.answer}</p>
							</div>
						</div>
					{/each}
				</div>
			</div>

            <p class="scroll-note">scroll inside the page for more questions.</p>
		</div>
	</div>
</section>

<style>
    .qa-section {
		min-height: auto;
		padding-top: 20px;
		scroll-margin-top: 170px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

    .qa-content {
        width: 100%;
        max-width: 1100px;
    }

    .qa-heading {
		text-align: center;
		margin-bottom: var(--space-lg);
	}

	.qa-heading h1 {
		font-family: var(--font-heading);
		font-size: var(--font-display);
		color: var(--color-text-primary);
		margin-bottom: var(--space-sm);
	}

	.qa-heading p {
		font-family: var(--font-body);
		font-size: var(--font-lg);
		color: var(--color-text-primary);
		margin: 0;
	}

    .notebook {
		width: min(86vw, 1120px);
		margin: 0 auto;
	}

	.notebook-page {
		position: relative;
		height: clamp(330px, 42vh, 390px);
		background-color: var(--qa-page-background);
		border: 2px solid var(--qa-page-border);
		border-radius: var(--radius-lg);
		padding: var(--space-lg) var(--space-xl);
		box-shadow: 14px 14px 0 var(--qa-page-shadow);
		overflow: hidden;
	}

    .notebook-page::before {
		content: '';
		position: absolute;
		inset: 0;
		background-image: repeating-linear-gradient(
			to bottom,
			transparent 0,
			transparent 37px,
			var(--qa-page-line) 38px
		);

		pointer-events: none;
	}

	.notebook-line {
		position: absolute;
		left: 70px;
		top: 0;
		bottom: 0;
		width: 3px;
		background-color: var(--qa-notebook-margin-line);
	}

    .page-bubbles {
		position: relative;
		z-index: 1;
		height: 100%;
		display: flex;
		flex-direction: column;
		gap: var(--space-lg);
		overflow-y: auto;
		padding-right: var(--space-md);
		scrollbar-width: thin;
		scrollbar-color: var(--qa-scrollbar-thumb) transparent;
	}

    .page-bubbles::-webkit-scrollbar {
		width: 8px;
	}

	.page-bubbles::-webkit-scrollbar-track {
		background: transparent;
	}

	.page-bubbles::-webkit-scrollbar-thumb {
		background-color: var(--qa-scrollbar-thumb);
		border-radius: var(--radius-pill);
	}

    .qa-pair {
		display: flex;
		flex-direction: column;
		gap: var(--space-sm);
		align-items: flex-start;
	}

	.qa-pair.right {
		align-items: flex-end;
	}

	.question-bubble,
	.answer-bubble {
		width: fit-content;
		max-width: 68%;
		padding: 0.75rem 1.4rem;
		color: var(--color-text-primary);
		box-shadow: 6px 6px 0 var(--qa-bubble-shadow);
	}

    .question-bubble {
		background-color: var(--qa-question-background);
		border-radius: 22px;
	}

	.answer-bubble {
		background-color: var(--qa-answer-background);
		border-radius: 22px;

		margin-left: var(--space-lg);
	}

	.qa-pair.right .answer-bubble {
		margin-left: 0;
		margin-right: var(--space-lg);
	}

    .question-bubble span,
	.answer-bubble span {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		width: 26px;
		height: 26px;
		border-radius: var(--radius-pill);
		background-color: var(--qa-letter-background);
		font-weight: bold;
		margin-right: var(--space-sm);
	}

	.question-bubble span {
	background-color: var(--qa-question-letter-background);
	color: var(--qa-question-letter-text);
	}

	.answer-bubble span {
		background-color: var(--qa-answer-letter-background);
		color: var(--qa-answer-letter-text);
	}

    .question-bubble p,
	.answer-bubble p {
		display: inline;
		font-family: var(--font-body);
		font-size: var(--font-base);
		line-height: 1.5;
		margin: 0;
	}

	.scroll-note {
		text-align: center;
		font-family: var(--font-body);
		font-size: var(--font-base);
		color: var(--color-text-primary);
		margin-top: var(--space-md);
	}

    @media (max-width: 800px) {

        .qa-section {
			padding: 100px var(--space-md) var(--space-xl);
			scroll-margin-top: 100px;
		}

		.qa-heading h1 {
			font-size: 3.2rem;
			line-height: 1.05;
			max-width: 340px;
			margin: 0 auto var(--space-md);
		}

		.qa-heading p {
			font-size: 1.45rem;
			line-height: 1.7;
			max-width: 340px;
			margin: 0 auto var(--space-md);
		}

		.notebook {
			width: 100%;
		}

		.notebook-page {
			height: 460px;
			padding: var(--space-md);
		}

		.notebook-line {
			left: 35px;
		}

        .question-bubble,
		.answer-bubble {
			max-width: 90%;
			padding: var(--space-md);
		}

		.qa-pair.right {
			align-items: flex-start;
		}

		.qa-pair.right .answer-bubble,
		.answer-bubble {
			margin-left: var(--space-md);
			margin-right: 0;
		}
    }
</style>