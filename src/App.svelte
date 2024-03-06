<script>
	let age = 0;
	let ageSubmitted = false;

	const ageSubmit = (e) => {
		age = e.target.value;
		ageSubmitted = true;
	};
</script>

<label for="text">Type your age:</label>
<input class="ageInput" type="number" id="age" bind:value={age} on:input={ageSubmit} />

{#if ageSubmitted}
	{#if age >= 18}
		<p class="message">You're an adult</p>
	{:else}
		<p class="message">You're young</p>
	{/if}
{/if}

<style>
	.ageInput {
		width: 100px;
		height: 30px;
		padding: 10px;
		text-align: center;
		color: blue;
	}
	.message {
		color: red;
	}
</style>
