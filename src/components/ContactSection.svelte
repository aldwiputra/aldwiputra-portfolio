<script>
	import ContactCard from './ContactCard.svelte';

	function backToTopHandler() {
		document.body.scrollIntoView({
			behavior: 'smooth'
		});
	}
</script>

<section id="contact">
	<div class="subtitle-container">
		<p>contact information</p>
	</div>
	<h2>Let's get in touch</h2>
	<div class="cards-wrapper flex">
		<ContactCard
			title="Github"
			name="aldiansyhdp@gmail.com"
			link="https://github.com/aldwiputra"
			icon="/github.svg"
		/>
		<ContactCard
			title="LinkedIn"
			name="Aldiansyah Dwi Putra"
			link="https://www.linkedin.com/in/aldwiputra/"
			icon="/linkedin.svg"
		/>
		<ContactCard
			title="Email"
			name="aldiansyhdp@gmail.com"
			link="mailto:aldiansyhdp@gmail.com"
			icon="/email.svg"
		/>
	</div>
	<div class="footer flex">
		<p>Copyright 2022 Ⓒ aldwiputra</p>
		<button on:click={backToTopHandler} class="back-to-top flex">
			<img src="/arrow-up.svg" alt="arrow top" />
			<p>Back to Top</p>
		</button>
	</div>
</section>

<style>
	section {
		position: relative;
		background-color: var(--color-grey-800);
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	section::before {
		position: absolute;
		content: '';
		inset: 0;
		width: 100%;
		height: 100%;
		background-color: var(--color-purple-800);
		z-index: -1;
		transform: scaleX(2);
	}

	.subtitle-container {
		background-color: var(--color-purple-700);
		width: fit-content;
		text-transform: uppercase;
		padding: 0.75rem 1.5rem;
		border-radius: 0.5rem;
		border: 1px solid black;
		font-family: 'Atkinson Hyperlegible', sans-serif;
		box-shadow: inset 0 1px 1px rgb(255 255 255 / 10%);
		margin-inline: auto;
		margin-block-start: 3rem;
	}

	h2 {
		font-size: clamp(2rem, 5vw, 3rem);
		line-height: 1;
		margin-block-start: 1.5rem;
	}

	.cards-wrapper {
		gap: 3rem;
		margin-block-start: 2.5rem;
		flex-wrap: wrap;
		justify-content: center;
	}

	.footer {
		padding-block: 1.5rem;
		border-top: 1px solid var(--color-purple-500);
		justify-content: space-between;
		width: 100%;
		margin-block-start: 4rem;
		font-family: 'Atkinson Hyperlegible', sans-serif;
		font-size: clamp(0.725rem, 3vw, 0.875rem);
	}

	.back-to-top {
		width: fit-content;
		align-items: center;
		cursor: pointer;
	}

	.back-to-top > p {
		margin-inline-start: 0.375rem;
		white-space: nowrap;
	}

	.back-to-top > img {
		height: 1rem;
	}

	button {
		background-color: transparent;
		border: none;
		color: rgba(var(--rgb-off-white));
	}

	button:hover {
		color: rgba(var(--rgb-white));
	}
</style>
