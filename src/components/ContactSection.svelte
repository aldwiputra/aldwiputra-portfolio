<section>
	<div class="subtitle-container">
		<p>contact information</p>
	</div>
	<h2>Let's get in touch</h2>
</section>

<style>
	section {
		position: relative;
		background-color: rgba(48, 48, 48, 1);
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	section::before {
		position: absolute;
		content: '';
		inset: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(48, 48, 48, 1);
		z-index: -1;
		transform: scaleX(2);
	}

	.subtitle-container {
		background-color: rgba(var(--rgb-grey-800));
		width: fit-content;
		text-transform: uppercase;
		padding: 0.75rem 1.5rem;
		border-radius: 0.5rem;
		border: 1px solid black;
		box-shadow: inset 0 1px 1px rgb(255 255 255 / 10%);
		margin-inline: auto;
		margin-block-start: 3rem;
	}

	h2 {
		font-size: clamp(2rem, 5vw, 3rem);
		margin-block-start: 1.5rem;
	}
</style>
