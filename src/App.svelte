<script>
	let age = 0;

	const ageSubmit = (e) => {
		age = (e.target.value);
	}
	
</script>

	<input type="number" id="age" bind:value={age} on:input{ageSubmit}>
		{#if age >= 18}
			<p>You're adult</p>
		{:else}
			<p>You're young</p>
		{/if}

