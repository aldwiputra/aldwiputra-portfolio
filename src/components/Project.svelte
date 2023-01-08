<script lang="ts">
	export let title: string;
	export let imgPaths: string[];
	export let techImgPaths: string[];

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
				<img src={techImgPaths[0]} alt="" />
			</div>
			<div class="img-container shadow">
				<img src={techImgPaths[1]} alt="" />
			</div>
			<div class="img-container shadow">
				<img src={techImgPaths[2]} alt="" />
			</div>
		</div>
	</div>
</div>

<style>
	.project-container {
		position: relative;
		padding-block: 2rem;
		border-bottom: 1px solid rgba(var(--rgb-grey-400));
		cursor: pointer;
	}

	.project-container:first-child {
		border-top: 1px solid rgba(var(--rgb-grey-400));
		margin-top: 1rem;
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
		margin-block-start: 1rem;
		margin-block-end: 1rem;
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
		width: clamp(3rem, 25vw, 12rem);
		min-width: 3rem;
	}

	.img-container {
		border-radius: 0.5rem;
		padding: 0.75rem;
		background-color: rgba(var(--rgb-grey-400));
	}

	.img-container img {
		width: 100%;
	}

	@media screen and (min-width: 45rem) {
		.img-container {
			padding: 1.25rem;
		}
	}

	@media screen and (min-width: 60rem) {
		.project-container:first-child {
			margin-top: 2.5rem;
		}

		.project-container:hover .gallery-container {
			opacity: 1;
			transform: scale(1) translateY(-30%);
		}

		.gallery-container {
			top: 0;
			right: 5%;
			z-index: 1;
			position: absolute;
			pointer-events: none;
			width: clamp(30rem, 35vw, 35rem);
			opacity: 0;
			will-change: transform;
			transform: scale(0.5) translateY(-30%);
			transition: all 100ms cubic-bezier(0.23, 1, 0.32, 1);
			transform-origin: top right;
		}

		.gallery-container > * {
			flex-grow: 1;
		}

		.img-container {
			padding: 1rem;
		}
	}
</style>
