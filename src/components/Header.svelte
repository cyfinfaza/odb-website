<script>
	import { onMount } from 'svelte';

	let scrolled = false;
	onMount((_) => {
		window.addEventListener('scroll', (_) => {
			scrolled = window.scrollY > 0;
		});
	});
</script>

<div class="header" class:scrolled>
	<!-- <h1>ODB</h1> -->
	<div class="horizPanel">
		<img src="/logo.png" class="logo" alt="" />
	</div>
	<div class="headerLinks">
		<a href="/">Home</a>
		<a href="/about">About</a>
		<a href="/contact-and-directions">Directions &amp; Contact</a>
		<a style="background-color: var(--accent-bg)" href="/donate-and-volunteer"
			>Donate &amp; Volunteer</a
		>
	</div>
</div>

<style>
	.header {
		display: flex;
		flex-direction: column;
		align-items: center;
		position: sticky;
		top: 0;
		background-color: var(--bg);
		z-index: 10;
		width: 100%;
		gap: 8px;
		padding: 12px;
		box-sizing: border-box;
		transition: 240ms;
	}
	@media screen and (max-height: 700px) {
		.header {
			position: static;
		}
		.header.scrolled {
			box-shadow: none;
		}
	}
	.header.scrolled {
		box-shadow: 0px 0px 10px #333c;
	}
	@supports (backdrop-filter: blur(24px)) {
		.header {
			backdrop-filter: blur(24px) saturate(180%);
			background-color: var(--header-bg);
		}
	}
	.header > * {
		margin: 0;
	}
	.logo {
		height: 72px;
		object-fit: contain;
	}
	.headerLinks {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		z-index: 10;
		gap: 8px;
	}
	.headerLinks > * {
		margin: 0;
	}
	.headerLinks > a {
		text-decoration: none;
		color: inherit;
		/* background-color: var(--header-link); */
		padding: 4px 9px;
		border-radius: 6px;
		transition: 120ms;
	}
	.headerLinks > a:hover {
		transform: translateY(-2px);
	}
	.titlefont {
		font-family: 'Raleway', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu,
			Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
		font-weight: 700;
		font-size: 1.5em;
	}
</style>
