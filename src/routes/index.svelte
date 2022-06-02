<script>
	import PageLayout from '../components/PageLayout.svelte';
	import { onMount } from 'svelte';

	let Carousel; // for saving Carousel component class
	let carousel; // for calling methods of the carousel instance
	onMount(async () => {
		// var el = document.querySelector('.odometer');

		// od = new Odometer({
		// 	el: el,
		// 	value: 333555
		// });
		// od.update(555);

		const module = await import('svelte-carousel');
		Carousel = module.default;
	});
	import Odo from '../components/Odo.svelte';
	let odoValue = 0;
	setTimeout(() => {
		odoValue = Math.floor(Math.random() * 1000000);
	}, 2000);
</script>

<svelte:head>
	<title>Our Daily Bread</title>
</svelte:head>

<PageLayout title="Welcome!" image="IMG_2049.jpg">
	<center> <h3>Our Daily Bread is a soup kitchen serving the greater York PA area</h3></center>

	<svelte:component this={Carousel} bind:this={carousel} class="carousel" autoplay>
		{#each ['IMG_2049.jpg', 'ODBVolunteer7-1.jpeg', 'IMG_1952.jpg', 'IMG_1962.jpg', 'IMG_1967.jpg', '2022-06-02 13.08.57.jpg', '2022-06-02 13.09.02.jpg', 'IMG_1987.jpg', 'IMG_1990.jpg', 'IMG_1999.jpg'] as image}
			<img src={'images/' + image} alt="" class="carouselImg" />
		{/each}
	</svelte:component>
	<!-- <Odo value={odoValue} nrDigits="3" dure="200" />
	<div align="center" id="odometer" class="odometer" /> -->
</PageLayout>

<style>
	.carouselImg {
		width: 100%;
		aspect-ratio: 3/2;
		object-fit: cover;
	}
</style>
