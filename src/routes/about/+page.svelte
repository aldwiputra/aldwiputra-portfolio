<script>
	import { fly } from 'svelte/transition';
	import SkillsSection from '../../components/SkillsSection.svelte';
</script>

<svg viewBox="0 0 59.5 12.5" in:fly={{ y: 100 }}>
	<style>
		text {
			font-weight: 400;
			letter-spacing: 0.25px;
		}
	</style>
	<linearGradient id="gr-simple" x1="0" y1="100%" x2="100%" y2="15%">
		<stop stop-color="rgb(52, 143, 183)" offset="25%" />
		<stop stop-color="rgba(190, 65, 234)" offset="85%" />
	</linearGradient>

	<defs>
		<radialGradient id="radialGradient">
			<stop offset="40%" stop-color="white" stop-opacity="1" />
			<stop offset="100%" stop-color="white" stop-opacity="0" />
		</radialGradient>

		<mask id="fade">
			<rect width="59.5" height="12.5" fill="url(#radialGradient)" />
		</mask>
	</defs>

	<path
		d="M52.063 0V19.108M44.625 0V19.108M37.188 0V19.108M29.75 0V19.108M22.313 0V19.108M14.875 0V19.108M7.438 0V19.028M0 14.366L59.5 14.366M0 9.584L59.5 9.584M0 4.802L59.5 4.802"
		stroke="#858586"
		stroke-opacity="0.25"
		stroke-width="0.034552845528455285"
		mask="url(#fade)"
	/>

	<text fill="url(#gr-simple" x="0" y="12">ABOUT</text>
</svg>

<p in:fly={{ opacity: 0, y: 100, delay: 200 }}>
	Hi, there! I am <span class="blue">Aldi</span> 👨🏼, a
	<span class="purple">Software Engineer </span>💻 based in Bandung, Indonesia. I started learning
	software development out of curiosity and immediately realized this field is something I want to
	do for the rest of my life. Not only that, learning new things has taught me more than the hard
	skill itself, it has also instilled the <span class="blue">growth mindset</span> 📈 in me.
</p>

<SkillsSection />

<style>
	svg {
		margin-block-start: 4rem;
	}

	path {
		pointer-events: none;
	}

	p {
		font-family: 'Atkinson Hyperlegible', sans-serif;
		margin-block-start: 4rem;
		font-size: clamp(1rem, 2vw, 1.5rem);
		font-weight: 400;
		max-width: 53ch;
		line-height: 1.5;
	}

	.blue {
		color: var(--color-blue-400);
	}
	.purple {
		color: var(--color-purple-400);
	}
</style>
