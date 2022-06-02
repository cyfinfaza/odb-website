<script>
	import Drum from './Drum.svelte';
	export let value;
	export let nrDigits = 3;
	export let dure = 200;
	function split(number) {
		return Array.from(number.toString().padStart(nrDigits, '0'));
	}
</script>

<div class="total">
	{#each split(value) as newNumber}
		<Drum {newNumber} {dure} />
	{/each}
</div>

<style>
	.total {
		display: block;
		margin: 5px;
	}
</style>
