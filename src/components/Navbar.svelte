<header>
	<div class="logo-container">
		<a href="/">
			<img class="logo-image" src="/logo-aldi.svg" alt="Logo Aldwiputra" />
		</a>
	</div>

	<div class="open-to-work-container" aria-hidden="true">
		<span class="shadow-green-light">
			<span class="green-light" />
		</span>

		<p>open to work</p>
	</div>

	<nav>
		<ul>
			<li><a href="#projects">projects</a></li>
			<li><a href="#contact">contact</a></li>
			<li><a href="#about">about</a></li>
		</ul>
	</nav>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		height: 4.5rem;
	}

	/* .logo-image {
		height: 1.75rem;
	} */

	.open-to-work-container > p {
		font-size: 0.875rem;
		font-weight: 300;
	}

	nav > ul {
		display: flex;
		text-transform: uppercase;
		font-size: 1rem;
		font-weight: 400;
	}

	nav > ul > li:not(:last-child) {
		margin-right: 1.25rem;
	}
</style>
