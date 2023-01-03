<script lang="ts">
	export let path: string;
	$: altText = path.replace('-', ' ').slice(0, -4);
</script>

<div class="shadow">
	<img src={path} alt={altText} />
</div>

<style>
	div {
		background-color: rgba(var(--rgb-grey-400));
		display: grid;
		place-items: center;
		border-radius: 0.5rem;
		width: 3.5rem;
		height: 3.5rem;
	}

	div:last-child {
		display: none;
	}

	img {
		height: 1.5rem;
	}

	@media screen and (min-width: 60rem) {
		div {
			width: 6rem;
			height: 6rem;
		}

		img {
			height: 3rem;
		}

		div:last-child {
			display: grid;
		}
	}
</style>
