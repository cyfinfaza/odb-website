<script>
	import ImageHeader from './ImageHeader.svelte';
	export let title;
	export let image;
</script>

<ImageHeader {title} {image} />
<div class="container">
	<main class="pageLayout">
		<slot />
	</main>
</div>

<style>
	.container {
		display: flex;
		justify-content: center;
		padding: 16px;
	}
	main {
		width: 100%;
		max-width: 800px;
	}
	.pageLayout {
		line-height: 1.6em;
	}
</style>
