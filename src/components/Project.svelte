<script lang="ts">
	export let title: string;
	export let imgPaths: string[];

	function turnPathIntoAltText(path: string) {
		return path.replace('-', ' ').slice(0, -4);
	}
</script>

<div class="project-container">
	<h3>{title}</h3>
	<div class="gallery-container flex">
		<div class="galleries shadow flex">
			<img src={imgPaths[0]} alt={turnPathIntoAltText(imgPaths[0])} />
			<img src={imgPaths[1]} alt={turnPathIntoAltText(imgPaths[1])} />
			<img src={imgPaths[2]} alt={turnPathIntoAltText(imgPaths[2])} />
		</div>
		<div class="tech-stack-container flex">
			<div class="img-container shadow">
				<img src="/react-icon.svg" alt="" />
			</div>
			<div class="img-container shadow">
				<img src="/typescript-icon.svg" alt="" />
			</div>
			<div class="img-container shadow">
				<img src="/nodejs-icon.svg" alt="" />
			</div>
		</div>
	</div>
</div>

<style>
	.project-container {
		position: relative;
		margin-block-start: 2.5rem;
		padding-block: 2rem;
		border-block: 2px solid rgba(var(--rgb-grey-subtext));
		cursor: pointer;
	}

	.project-container:hover h3 {
		background: linear-gradient(45deg, rgba(239, 88, 68, 1) 10%, rgba(75, 209, 53, 1) 90%);
		-webkit-text-fill-color: transparent;
		-moz-text-fill-color: transparent;
		-webkit-background-clip: text;
		background-clip: text;
	}

	h3 {
		position: relative;
		z-index: 0;
		width: fit-content;
		font-size: clamp(1rem, 4vw, 2rem);
		font-family: 'Atkinson Hyperlegible', sans-serif;
		font-weight: 400;
		text-transform: uppercase;
		letter-spacing: 0.125rem;
	}

	img {
		min-width: 0;
	}

	.gallery-container {
		gap: 1rem;
		align-items: flex-start;
	}

	.galleries {
		border-radius: 0.5rem;
		padding: 1rem 2rem;
		justify-content: center;
		align-items: center;
		background-color: rgba(var(--rgb-grey-400));
	}

	.tech-stack-container {
		flex-direction: column;
		gap: 1rem;
		width: 10rem;
		min-width: 4rem;
	}

	.img-container {
		border-radius: 0.5rem;
		padding: 1rem;
		background-color: rgba(var(--rgb-grey-400));
	}

	.img-container img {
		width: 100%;
	}

	@media screen and (min-width: 60rem) {
		.project-container:hover .gallery-container {
			opacity: 1;
			transform: scale(1) translateY(-30%);
		}

		.gallery-container {
			top: 0;
			right: 5%;
			z-index: 1;
			position: absolute;
			max-width: 35rem;
			transform: translateY(-30%);
			pointer-events: none;
			width: fit-content;
			opacity: 0;
			transform: scale(0.5) translateY(-30%);
			transition: all 100ms cubic-bezier(0.23, 1, 0.32, 1);
			transform-origin: top right;
		}
	}
</style>
