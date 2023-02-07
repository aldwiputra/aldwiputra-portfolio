<script lang="ts">
	export let title: string;
	export let totalExperience: string;
	export let imgSrc: string;
</script>

<div class="card shadow flex">
	<div class="img-wrapper flex" data-justi-align="sb-center">
		<img src={imgSrc} alt={imgSrc} />
	</div>

	<div class="text-wrapper">
		<h3>{title}</h3>
		<p>{totalExperience}</p>
	</div>
</div>

<style>
	.card {
		background-color: var(--color-purple-600);
		border-radius: 0.5rem;
		padding: 1.25rem 2rem;
		gap: 1.5em;
		min-width: 19rem;
		align-items: center;
	}

	.img-wrapper {
		background-color: rgba(190, 65, 234, 0.075);
		border: 2px solid rgba(190, 65, 234);
		width: 3.5rem;
		height: 3.5rem;
		padding: 0.75rem;
		border-radius: 0.375rem;
	}

	.text-wrapper {
		font-family: 'Atkinson Hyperlegible', sans-serif;
	}

	h3 {
		font-weight: 400;
		font-size: 1.5rem;
	}

	p {
		font-size: 1rem;
		color: var(--color-purple-subtext);
	}
</style>
