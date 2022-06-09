<script>
	import PageLayout from '../components/PageLayout.svelte';
</script>

<svelte:head>
	<title>Contact & Directions | Our Daily Bread</title>
</svelte:head>

<PageLayout title="Contact & Directions" image="IMG_1990.jpg">
	<h2>Contact Information</h2>
	<p>
		Email: <a href="mailto:ourdailybreadyork@gmail.com" >ourdailybreadyork@gmail.com</a>
	</p>
	<p>
		Phone Number: <a href="tel:+1 717-848-1674" >717-848-1674</a>
	</p>
	<h2>Directions</h2>
	<iframe
		src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d296.06151807653964!2d-76.72506156740124!3d39.95756819840454!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c88eaefefdbef7%3A0xeaf78afcf135395f!2sOur%20Daily%20Bread%20Soup%20Kitchen!5e0!3m2!1sen!2sus!4v1654185298580!5m2!1sen!2sus"
		allowfullscreen=""
		loading="lazy"
		referrerpolicy="no-referrer-when-downgrade"
		title="Map of Our Daily Bread"
	/>
</PageLayout>

<style>
	iframe {
		width: 100%;
		height: 400px;
		border: none;
		border-radius: 8px;
	}
</style>
