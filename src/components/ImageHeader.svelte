<script>
	export let title;
	export let image;
</script>

<div class="container">
	<img class="headerImage" src={'/images/' + image} alt="" />
	<h1 class="title dim">{title || ''}</h1>
</div>

<style>
	img {
		border-radius: 0;
	}
	.container {
		display: flex;
		align-items: center;
		justify-content: center;
		position: relative;
	}
	.headerImage {
		width: 100%;
		height: 40vh;
		object-fit: cover;
	}
	.title {
		position: absolute;
		width: 100%;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 4rem;
		font-weight: 900;
		margin: 0;
		text-align: center;
	}
	@media screen and (max-width: 500px) {
		.title {
			font-size: 3rem;
		}
	}
	.dim {
		background-color: var(--image-dim);
	}
</style>
