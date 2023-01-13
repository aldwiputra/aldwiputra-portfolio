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
		width: clamp(3rem, 14vw, 5.5rem);
		height: clamp(3rem, 14vw, 5.5rem);
	}

	div:last-child {
		display: none;
	}

	img {
		height: clamp(1.75rem, 8vw, 3rem);
	}

	@media screen and (min-width: 60rem) {
		div:last-child {
			display: grid;
		}
	}
</style>
