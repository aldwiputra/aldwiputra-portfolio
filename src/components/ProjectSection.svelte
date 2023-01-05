<script lang="ts">
	import Project from './Project.svelte';
	import TabButton from './TabButton.svelte';
</script>

<section>
	<h2>Projects <span>.</span></h2>
	<div class="tab-buttons-container flex">
		<TabButton path="all-icon.svg" text="All" />
		<TabButton path="webdev-icon.svg" text="Web" />
		<TabButton path="mobile-icon.svg" text="Mobile" />
	</div>
	<Project
		title="Expenditura"
		imgPaths={['/expenditura-onboard.webp', '/expenditura-home.webp', '/expenditura-dialog.webp']}
	/>
</section>

<style>
	section {
		margin-block: 5rem;
	}

	h2 {
		font-size: clamp(2rem, 5vw, 3rem);
		font-weight: 600;
	}

	span {
		color: rgba(var(--rgb-orange));
	}

	.tab-buttons-container {
		display: none;
		gap: 0.75rem;
		margin-block-start: 1.5rem;
	}

	@media screen and (min-width: 60rem) {
		.tab-buttons-container {
			display: flex;
		}
	}
</style>
