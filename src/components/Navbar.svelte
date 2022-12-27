<header>
	<a class="logo-container" href="/">
		<img class="logo-image" src="/logo-aldi.svg" alt="Logo Aldwiputra" />
	</a>

	<div class="open-to-work-container" aria-hidden="true">
		<span class="green-light" />
		<p>open to work</p>
	</div>

	<nav>
		<ul>
			<li><a href="#projects">projects</a></li>
			<li><a href="#contact">contact</a></li>
			<li>
				<a href="#about"
					>about <svg
						width="12"
						height="12"
						viewBox="0 0 13 13"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M12.25 10.5C12.6642 10.5 13 10.1642 13 9.74998L13 0.75C13 0.335787 12.6642 1.68587e-06 12.25 1.3487e-06L3.25 0C2.83579 0 2.5 0.335786 2.5 0.749999C2.5 1.16421 2.83579 1.5 3.25 1.5L10.4393 1.5L0.21967 11.7197C-0.0732233 12.0125 -0.0732234 12.4874 0.21967 12.7803C0.512563 13.0732 0.987437 13.0732 1.28033 12.7803L11.5 2.56066L11.5 9.74998C11.5 10.1642 11.8358 10.5 12.25 10.5Z"
							fill="#E2E8F0"
						/>
					</svg></a
				>
			</li>
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

	span {
		display: block;
	}

	.logo-container {
		width: 8vw;
	}

	.logo-image {
		width: 100%;
	}

	.open-to-work-container {
		padding: 0.375rem 1.5rem;
		display: none;
		justify-content: center;
		align-items: center;
		border-radius: 1.5rem;
		border: 1px solid rgba(var(--rgb-off-white));
	}

	.open-to-work-container p {
		font-size: 0.75rem;
		font-weight: 300;
		margin-left: 0.75rem;
		transform: translateY(-8%);
	}

	.green-light {
		--opacity: 0.7;

		width: 0.5rem;
		height: 0.5rem;
		background-color: rgba(var(--rgb-green));
		border-radius: 50%;
		box-shadow: 0 0 0.6rem 0.1rem rgba(var(--rgb-green), var(--opacity));
	}

	nav {
		display: none;
	}

	nav ul {
		display: flex;
		text-transform: uppercase;
		font-size: 0.875rem;
		font-weight: 400;
	}

	nav li:not(:last-child) {
		margin-right: 3rem;
	}

	svg {
		transform: scale(0.9) translateY(10%);
		margin-left: 0.125rem;
	}

	@media screen and (min-width: 60rem) {
		.open-to-work-container {
			display: flex;
		}

		nav {
			display: block;
		}
	}
</style>
