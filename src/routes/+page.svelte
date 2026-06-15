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

	const carouselImages = ['IMG_2049.jpg', 'ODBVolunteer7-1.jpeg', 'IMG_1952.jpg', 'IMG_1962.jpg', 'IMG_1999.jpg', 'IMG_2007.jpg', 'IMG_1978.jpg', 'IMG_1967.jpg', 'IMG_2033.jpg', '2022-06-02 13.08.57.jpg', '2022-06-02 13.09.02.jpg', 'IMG_1987.jpg', 'IMG_1990.jpg', 'IMG_1999.jpg'];
	let carouselImageModes = carouselImages.map(img=>"lazy");
</script>

<svelte:head>
	<title>Our Daily Bread</title>
</svelte:head>

<PageLayout title="Welcome!" image="IMG-7654.jpg">
	<h2>What We Do</h2>

	<!-- What we did for giving local york in may 2023 -->
	<!-- <h4>
		Give Local York is coming! On May 4th and 5th, join our campaign and help us reach our goal of
		$9,000 through Give Local York's Day of Giving.
	</h4>
	<a class="button donateButton" href="/givegab-donate.html">Donate Now </a> -->
	<p> 
		Our Daily Bread Soup Kitchen serves meals to the residents of York, Pennsylvania. We are a small
		nonprofit organization that relies on donations of food and time from individuals and businesses
		around York County. We serve breakfast and lunch, Monday through Friday. We make it a point to
		not discriminate against anyone who comes in to eat; all are welcome to a hot meal!
	</p>

	<img src="/images/ODB 40 Years.jpg" alt="Commemorative banner marking 40 years of service at Our Daily Bread soup kitchen in York Pennsylvania" />

	<div class="donateCard">
	<h2>List of donation needs:</h2>

	<ul>
		<li>Sugar</li>
		<li>Ground coffee</li>
		<li>Tea bags (black tea)</li>
		<li>Ketchup</li>
		<li>Hot Sauce</li>
	  </ul>
</div>
	<div class="donateCard">
		<h2>Donate Online</h2>
		<h4>We now take donations through <a href="https://www.paypal.com/donate/?hosted_button_id=EBWCUCQWWVQW8">PayPal</a>!</h4>
	</div>
<div class="donateCard">
	<h2>News</h2>
	<section class="thankYouFeature">
	<div class="thankYouText">
		<p>
			Thank you so much to Kimberly and the Reworld Waste team for collecting Gatorade and
			Propel Fitness Water to help our patrons stay hydrated through the summer! The team
			brought 40 cases of electrolyte drinks to Our Daily Bread—the stack is taller than Paula!!
		</p>

		<p>We are so grateful to you, friends!</p>
	</div>

	<div class="thankYouImages">
		<img src={"images/IMG_4651.jpeg"} class="thankYouImage" alt="Reworld Waste team members delivering cases of donated sports drinks to soup kitchen volunteers" />
		<img src={"images/IMG_4652.jpeg"} class="thankYouImage" alt="Stacks of donated Gatorade and Propel fitness water bottles arranged in the soup kitchen storage area" />
		<img src={"images/IMG_4653.jpeg"} class="thankYouImage" alt="Volunteers at Our Daily Bread standing beside donated beverage cases with appreciation" />
	</div>
</section>
</div>
	
	<svelte:component this={Carousel} bind:this={carousel} class="carousel" autoplay>
		{#each carouselImages as image, index}
			<img src={'images/' + image} alt="" class="carouselImg" loading={carouselImageModes[index]} on:load={e=>{
				const imageElement = e.target
				const localInterval = setInterval(()=>{
					if (imageElement.complete) {
						carouselImageModes[(index+1)%carouselImages.length] = "eager";
						console.log("loaded carousel image", index)
						clearInterval(localInterval);
					}
				}, 1000)
			}} />
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

	.donateCard {
		background: linear-gradient(135deg, #fff8ec 0%, #fff1d6 100%);
		border: 1px solid #f0d6a3;
		border-radius: 16px;
		box-shadow: 0 12px 24px rgba(0, 0, 0, 0.08);
		padding: 1.5rem;
		margin: 2rem 0;
	}

	.donateCard h2 {
		margin-top: 0;
		color: #000000;
	}

	.donateCard h4 {
		margin: 0.5rem 0 0;
		font-weight: 500;
		line-height: 1.5;
	}

	.donateCard a {
		color: #000000;
		text-decoration: underline;
	}

	.donateButton {
		padding: 4px 10px;
	}

.thankYouFeature {
	margin: 2rem 0;
}

.thankYouImage {
	display: block;
	width: 100%;
	max-width: 700px;
	margin: 1rem auto;
	border-radius: 8px;
}

.thankYouImages img {
	width: 100%;
	height: auto;
	border-radius: 8px;
	display: block;
}

@media (max-width: 700px) {
	.thankYouImages {
		grid-template-columns: 1fr;
	}
}
</style>
