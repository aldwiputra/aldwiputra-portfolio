<script>
	import SkillItem from './SkillItem.svelte';
</script>

<section>
	<h2>Skills<span class="purple"> .</span></h2>
	<div class="skills-wrapper flex">
		<SkillItem
			title="Frontend Dev"
			totalExperience="1 Year Experience"
			imgSrc="/frontend-icon.svg"
		/>
		<SkillItem title="UI Design" totalExperience="1 Year Experience" imgSrc="/ui-icon.svg" />
		<SkillItem
			title="Android Dev"
			totalExperience="4 Month Experience"
			imgSrc="/android-icon2.svg"
		/>
		<SkillItem title="Database" totalExperience="6 Month Experience" imgSrc="/database-icon.svg" />
		<SkillItem title="Backend Dev" totalExperience="1 Year Experience" imgSrc="/backend-icon.svg" />
	</div>
</section>

<style>
	section {
		margin-block: 6rem;
	}

	h2 {
		font-size: clamp(2rem, 5vw, 3rem);
		font-weight: 600;
	}

	.purple {
		color: var(--color-blue-400);
	}

	.skills-wrapper {
		margin-block-start: 2rem;
		gap: 2rem;
		flex-wrap: wrap;
		flex-grow: 1;
	}
</style>
