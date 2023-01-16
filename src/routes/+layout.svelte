<script lang="ts">
	import Container from '../components/Container.svelte';
	import Navbar from '../components/Navbar.svelte';
	import '../global.css';
</script>

<Container>
	<Navbar />
	<slot />
</Container>
