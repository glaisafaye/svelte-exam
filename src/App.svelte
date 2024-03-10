<script>
	let age = 0;
	let ageSubmitted = false;

	const ageSubmit = (e) => {
		age = e.target.value;
		ageSubmitted = age !== "";
	};
</script>

<style>
	.container {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
	}
</style>

<div class="relative h-screen">
	<div class="container mx-auto flex flex-col items-center">
		<!-- svelte-ignore a11y-label-has-associated-control -->
		<label class="text-gray-700 font-bold mb-2 transition">Type your age:</label>
		<input type="number" placeholder="Type here" class="input input-bordered w-full max-w-xs p-4 transition" id="age" bind:value={age} on:input={ageSubmit} />
		{#if ageSubmitted}
			{#if age >= 18}
				<p class="text-lg text-green-500 transition mt-2">You're an adult</p>
			{:else}
				<p class="text-lg text-red-500 transition mt-2">You're young</p>
			{/if}
		{/if}
	</div>
</div>
