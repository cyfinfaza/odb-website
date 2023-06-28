<script>
	import PageLayout from '../../components/PageLayout.svelte';
</script>

<svelte:head>
	<title>Donate or Volunteer | Our Daily Bread</title>
</svelte:head>

<PageLayout title="Donate or Volunteer" image="donatePic.JPG">
	<h2>Volunteering</h2>
	<p>If interested in volunteering, reach out to us!</p>
	<p>
		Email: <a href="mailto:ourdailybreadyork@gmail.com">ourdailybreadyork@gmail.com</a>
	</p>
	<p>
		Phone Number: <a href="tel:+1 717-848-1674">717-848-1674</a>
	</p>
	<p>Please provide us with your name, email address, phone number, and availability.</p>
	<h2>Food Donations</h2>
	<p>
		Individual donations of desserts, produce, or nonperishable goods can be dropped off at <br
		/>331 S George St<br>
		York, PA 17401.
	</p>
	<p>If you have a casserole or other transportable goods, please give us a call (717-848-1674)!</p>
	<h2>Monetary Donations</h2>
	<p>We take online donations via facebook. Click below to donate!</p>
	<p>
		<a
			class="button donateButton"
			href="https://www.facebook.com/ourdailybreadyork"
			>Donate Online</a
		>
	</p>
	<p>
		Or if you prefer, you can <strong>send us a check</strong> made out to Our Daily Bread York.<br>
		PO BOX 548 <br>
		York, PA 17405
	</p>
	<p>Just <strong> $50 can provide 25 meals! </strong></p>
	<p>We thank you for your support and generosity!</p>
	<img src="/images/ODBVolunteer8.jpg" alt="" />
</PageLayout>

<style>
	.donateButton {
		padding: 4px 10px;
	}
</style>
