<script lang="ts">
	import { onMount } from 'svelte';

	let time = new Date();
	$: formattedTime = time.toLocaleTimeString([], {
		timeStyle: 'short'
	});
	$: timeOfDay = time.getHours() < 12 ? 'Morning' : time.getHours() < 18 ? 'Afternoon' : 'Night';

	onMount(() => {
		const timer = setInterval(() => {
			time = new Date();
		}, 30000);

		return () => {
			clearInterval(timer);
		};
	});
</script>

<div>
	<p class="greeting">
		Good {timeOfDay}
	</p>
	<p class="time">
		{formattedTime}!
	</p>
</div>

<style>
	div {
		font-family: 'Atkinson Hyperlegible', sans-serif;
		font-size: 14px;
	}

	p {
		text-align: end;
		line-height: 1.2;
	}

	.time {
		color: var(--color-grey-subtext);
		font-size: 12px;
	}

	@media screen and (min-width: 60rem) {
		div {
			display: none;
		}
	}
</style>
