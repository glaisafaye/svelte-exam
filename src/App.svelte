<script>
	let age = 0;

	const ageSubmit = (e) => {
		age = e.target.value;
	};
</script>

<input class="ageInput" type="number" id="age" bind:value={age} on:input{ageSubmit} />
{#if age >= 18}
	<p class="messagGGe">You're adult</p>
{:else}
	<p class="message">You're young</p>
{/if}

<style>
	.ageInput {
		width: 100px;
		height: 30px;
		padding: 10px;
		text-align: center;
	}
	.message{
		color: red;
	}
</style>