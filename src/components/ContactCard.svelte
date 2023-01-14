<script lang="ts">
	export let title: string;
	export let name: string;
	export let link: string;
	export let icon: string;

	$: backgroundColor =
		title === 'Github'
			? 'rgba(var(--rgb-black-github))'
			: title === 'LinkedIn'
			? 'rgba(var(--rgb-blue-linkedin))'
			: 'rgba(var(--rgb-red-email))';
</script>

<div class="card-container shadow">
	<div class="icon-wrapper" style={`background-color: ${backgroundColor}`}>
		<img src={icon} alt="icon" />
	</div>

	<p class="title">{title}</p>
	<div class="line-separator" />
	<p class="name">{name}</p>

	<div class="link-box">
		<a class="flex" target="_blank" rel="noreferrer" href={link}>
			<p class="link">{link}</p>
			<svg
				width="20"
				height="20"
				viewBox="0 0 20 20"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					d="M12.9163 1.875C12.9163 1.52982 13.1962 1.25 13.5413 1.25H18.1247C18.4699 1.25 18.7497 1.52982 18.7497 1.875V6.45833C18.7497 6.80351 18.4699 7.08333 18.1247 7.08333C17.7795 7.08333 17.4997 6.80351 17.4997 6.45833V3.38388L12.3166 8.56694C12.0725 8.81102 11.6768 8.81102 11.4327 8.56694C11.1887 8.32286 11.1887 7.92713 11.4327 7.68305L16.6158 2.5H13.5413C13.1962 2.5 12.9163 2.22018 12.9163 1.875Z"
					fill="#DFE6EE"
				/>
				<path
					d="M2.08301 3.54167C2.08301 2.73625 2.73593 2.08333 3.54134 2.08333H10.6247C10.9699 2.08333 11.2497 2.36316 11.2497 2.70833C11.2497 3.05351 10.9699 3.33333 10.6247 3.33333H3.54134C3.42628 3.33333 3.33301 3.42661 3.33301 3.54167V16.4583C3.33301 16.5734 3.42628 16.6667 3.54134 16.6667H16.458C16.5731 16.6667 16.6663 16.5734 16.6663 16.4583V9.375C16.6663 9.02982 16.9462 8.75 17.2913 8.75C17.6365 8.75 17.9163 9.02982 17.9163 9.375V16.4583C17.9163 17.2637 17.2634 17.9167 16.458 17.9167H3.54134C2.73593 17.9167 2.08301 17.2637 2.08301 16.4583V3.54167Z"
					fill="#DFE6EE"
				/>
			</svg>
		</a>
	</div>
</div>

<style>
	.card-container {
		background-color: rgba(var(--rgb-grey-400));
		border-radius: 1rem;
		padding: 1.5rem;
		min-width: 19rem;
		overflow: hidden;
	}

	.icon-wrapper {
		border-radius: 0.5rem;
		padding-block: 2rem;
	}

	img {
		max-width: 5rem;
		margin-inline: auto;
	}

	.title {
		margin-block-start: 1.5rem;
		font-size: 1.5rem;
		font-weight: 600;
	}

	.name {
		font-size: 0.875rem;
		margin-block-start: 0.75rem;
	}

	.link {
		font-size: 0.75rem;
		max-width: 22ch;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}

	a {
		justify-content: space-between;
		align-items: center;
		margin-block-start: 0.75rem;
		background-color: rgba(var(--rgb-grey-200));
		border-radius: 0.25rem;
		padding: 0.375rem 0.75rem;
	}

	svg {
		width: 0.75rem;
	}

	.line-separator {
		height: 1px;
		background-color: rgba(var(--rgb-grey-200), 0.4);
		transform: scaleX(1.5);
		margin-block-start: 0.75rem;
	}

	.name,
	.link-box {
		font-family: 'Atkinson Hyperlegible', sans-serif;
		will-change: transform;
		transition: transform 50ms linear;
	}

	.link-box:hover {
		transform: scale(1.05);
	}

	.link-box:hover .link {
		text-decoration: underline;
	}
</style>
