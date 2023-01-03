<script>
	import TechBox from './TechBox.svelte';
</script>

<section>
	<div class="section-container">
		<h1>I am a <br /> <span class="fullstack">fullstack <br /></span> shaman</h1>
		<div class="subtext-container shadow">
			<p>specialized in sprinkling magic onto the <span>www.</span></p>
		</div>

		<div class="techbox-container flex">
			<TechBox path="react-icon.svg" />
			<TechBox path="firestore-icon.svg" />
			<TechBox path="nodejs-icon.svg" />
			<TechBox path="svelte-icon.svg" />
			<TechBox path="typescript-icon.svg" />
			<TechBox path="db-icon.svg" />
		</div>
	</div>
</section>

<style>
	section {
		width: 100%;
		z-index: 1;
		position: relative;
		padding-block: 4.5rem;
	}

	section::before {
		z-index: 0;
		position: absolute;
		inset: 0;
		width: 100%;
		height: 100%;
		content: '';
		background-image: url('/grid-lines.svg');
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
		-webkit-mask-image: radial-gradient(rgba(0, 0, 0, 1) 15%, transparent 76%);
		-webkit-mask-size: 100%;
		-webkit-mask-repeat: no-repeat;
		-webkit-mask-position: center;
		mask-image: radial-gradient(rgba(0, 0, 0, 1) 15%, transparent 76%);
		mask-size: 100%;
		mask-repeat: no-repeat;
		mask-position: center;
	}

	h1 {
		position: relative;
		font-size: clamp(3rem, 8vw, 6rem);
		line-height: 1.1;
	}

	.section-container {
		width: fit-content;
		text-align: center;
		margin-inline: auto;
	}

	.fullstack {
		background: linear-gradient(45deg, rgba(239, 88, 68, 1) 10%, rgba(75, 209, 53, 1) 120%);
		-webkit-text-fill-color: transparent;
		-moz-text-fill-color: transparent;
		-webkit-background-clip: text;
		background-clip: text;
	}

	.subtext-container {
		margin-top: 2.25rem;
		font-family: 'Atkinson Hyperlegible', sans-serif;
		font-size: clamp(0.75rem, 3vw, 1.25rem);
		padding: 0.5rem 1rem;
		background-color: rgba(var(--rgb-grey-800));
		color: rgba(var(--rgb-grey-subtext));
		border-radius: 0.5rem;
		width: fit-content;
		margin-inline: auto;
	}

	.subtext-container span {
		color: rgba(var(--rgb-orange));
		font-weight: bold;
		font-style: italic;
	}

	.techbox-container {
		gap: 1rem;
		margin-top: 3.5rem;
		margin-inline: auto;
		width: fit-content;
	}

	@media screen and (min-width: 60rem) {
		.techbox-container {
			gap: 2.5rem;
		}
	}
</style>
