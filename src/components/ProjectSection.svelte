<script lang="ts">
	import Project from './Project.svelte';
	import TabButton from './TabButton.svelte';
</script>

<section id="projects">
	<h2>Projects <span>.</span></h2>
	<div class="tab-buttons-container flex">
		<TabButton path="all-icon.svg" text="All" />
		<TabButton path="webdev-icon.svg" text="Web" />
		<TabButton path="mobile-icon.svg" text="Mobile" />
	</div>
	<div class="projects-container">
		<Project
			title="Expenditura"
			imgPaths={['/expenditura-onboard.webp', '/expenditura-home.webp', '/expenditura-dialog.webp']}
			techImgPaths={['/android-icon.svg', '/kotlin-icon.svg', '/mysql-icon.svg']}
		/>
		<Project
			title="Watchflix"
			imgPaths={['/watchflix-home.webp', '/watchflix-detail.webp', '/watchflix-chat.webp']}
			techImgPaths={['/android-icon.svg', '/kotlin-icon.svg', '/firebase-colored.svg']}
		/>
		<Project
			title="RPS Game"
			imgPaths={['/rps-splash.webp', '/rps-home.webp', '/rps-option.webp']}
			techImgPaths={['/android-icon.svg', '/kotlin-icon.svg', '/db-icon.svg']}
		/>
	</div>
</section>

<style>
	section {
		margin-block-start: 10rem;
		margin-block-end: 7rem;
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
		section {
			margin-block-start: 7rem;
		}

		.tab-buttons-container {
			display: flex;
		}
	}
</style>
