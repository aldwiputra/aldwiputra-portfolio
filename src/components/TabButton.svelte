<script lang="ts">
	export let path: string;
	export let text: string;
	$: altText = path.replace('-', ' ').slice(0, -4);
</script>

<div
	class="flex"
	data-justi-align="sb-center"
	style={text !== 'All'
		? 'border: 1px solid var(--color-purple-subtext); color: var(--color-purple-subtext); ; cursor: not-allowed;'
		: 'border: 1px solid rgba(var(--rgb-off-white));color: rgba(var(--rgb-off-white)); cursor: not-allowed;'}
>
	<img src={path} alt={altText} />
	<p>
		{text}
	</p>
</div>

<style>
	div {
		font-size: 1rem;
		cursor: auto;
		border-radius: 1rem;
		border: 1px solid rgba(var(--rgb-off-white));
		padding: 0.25rem 1rem;
	}

	img {
		height: 1em;
		margin-inline-end: 0.5rem;
	}

	p {
		display: block;
		font-family: 'Atkinson Hyperlegible', sans-serif;
	}
</style>
