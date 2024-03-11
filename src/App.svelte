<script>
	let age = 0;
	let ageSubmitted = false;

	const ageSubmit = (e) => {
		age = e.target.value;
		ageSubmitted = age !== "";
	};
</script>

<div class="flex justify-center items-center h-screen bg-gray-500">
	<div class="bg-gray-200 p-10 rounded-lg shadow-lg">
		<div class="flex flex-col items-center">
			<label class="text-gray-700 font-bold mb-2">Type your age:</label>
			<input type="number" placeholder="Type here" class="input input-bordered w-full max-w-xs p-4 transition" id="age" bind:value={age} on:input={ageSubmit} />
			{#if ageSubmitted}
				{#if age >= 18}
					<p class="text-lg text-green-500 mt-2">You're an adult</p>
				{:else}
					<p class="text-lg text-red-500 mt-2">You're young</p>
				{/if}
			{/if}
		</div>
	</div>
</div>
