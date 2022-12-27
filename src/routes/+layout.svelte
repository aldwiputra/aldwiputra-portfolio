<script lang="ts">
	import Container from '../components/Container.svelte';
	import Navbar from '../components/Navbar.svelte';
	import '../global.css';
</script>

<Container>
	<Navbar />
	<slot />
</Container>

<style>
	:global(:root) {
		--color-black: rgba(1, 1, 1, 1);

		--color-grey-800: rgba(35, 35, 35, 1);
		--color-grey-600: rgba(51, 51, 51, 1); /* background */
		--color-grey-400: rgba(62, 61, 61, 1); /* card background */
		--color-grey-200: rgba(97, 97, 97, 1);
		--color-grey-subtext: rgba(138, 139, 141, 1);

		--color-off-white: rgba(226, 232, 240, 1);
		--color-white: rgba(255, 255, 255, 1);

		--color-orange: rgba(235, 91, 68, 1);
		--color-green: rgba(75, 209, 53, 1);

		--color-black-github: rgba(41, 41, 39, 1);
		--color-blue-linkedin: rgba(19, 110, 150, 1);
		--color-red-email: rgba(187, 49, 49, 1);
	}
</style>
