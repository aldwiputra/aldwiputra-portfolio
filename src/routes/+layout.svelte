<script lang="ts">
	import Container from '../components/Container.svelte';
	import Navbar from '../components/Navbar.svelte';
	import '../global.css';
</script>

<Container>
	<img src="/mesh.png" alt="mesh effect" />
	<Navbar />
	<slot />
</Container>

<style>
	img {
		position: absolute;
		inset: 0;
		z-index: -2;
		transform: scale(150%);
		transform-origin: center;
		opacity: 0.75;
	}

	@media screen and (min-width: 60rem) {
		img {
			transform: scale(100%);
		}
	}
</style>
