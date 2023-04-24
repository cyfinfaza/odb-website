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

<PageLayout title="Welcome!" image="IMG-7654.jpg">
	<h2>What We Do</h2>

	<h4>
		Give Local York is coming! On May 4th and 5th, join our campaign and help us reach our goal of
		$9,000 through Give Local York's Day of Giving.
	</h4>
	<a class="button donateButton" href="/givegab-donate/">Donate Now </a>
	<p>
		Our Daily Bread Soup Kitchen serves meals to the residents of York, Pennsylvania. We are a small
		nonprofit organization that relies on donations of food and time from individuals and businesses
		around York County. We serve breakfast and lunch, Monday through Friday. We make it a point to
		not discriminate against anyone who comes in to eat; all are welcome to a hot meal!
	</p>

	<h2>Gallery</h2>
	<svelte:component this={Carousel} bind:this={carousel} class="carousel" autoplay>
		{#each ['IMG_2049.jpg', 'ODBVolunteer7-1.jpeg', 'IMG_1952.jpg', 'IMG_1962.jpg', 'IMG_1999.jpg', 'IMG_2007.jpg', 'IMG_1978.jpg', 'IMG_1967.jpg', 'IMG_2033.jpg', '2022-06-02 13.08.57.jpg', '2022-06-02 13.09.02.jpg', 'IMG_1987.jpg', 'IMG_1990.jpg', 'IMG_1999.jpg'] as image}
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

	.donateButton {
		padding: 4px 10px;
	}
</style>
