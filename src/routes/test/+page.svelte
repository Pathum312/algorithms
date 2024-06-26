<script lang="ts">
	import { onMount } from 'svelte';

	const sorted = [11, 12, 22, 25, 64];
	$: unsorted = [64, 25, 12, 22, 11];
	$: firstValueIndex = '';
	$: secondValueIndex = '';

	// Swap the places of the values in the array
	const swap = (firstIndex, secondIndex) => {
		firstValueIndex = firstIndex;
		secondValueIndex = secondIndex;

		[unsorted[firstIndex], unsorted[secondIndex]] = [unsorted[secondIndex], unsorted[firstIndex]];
	};

	const selectionSort = () => {
		let min_idx, i, j;

		for (i = 0; i < unsorted.length; i++) {
			min_idx = i;
			for (j = i + 1; j < unsorted.length; j++) {
				if (unsorted[j] < unsorted[min_idx]) min_idx = j;
			}
			if (min_idx !== i) swap(min_idx, i);
		}
	};

	const reset = () => {
		firstValueIndex = '';
		secondValueIndex = '';
		unsorted = [64, 25, 12, 22, 11];
	};
</script>

<div class="container">
	<div class="card">
		<p>Unsorted Array: [{unsorted}]</p>
		<div class="array">
			{#each unsorted as item, index}
				<div
					class="item"
					class:highlighted-green={index === firstValueIndex || index === secondValueIndex}
				>
					{item}
				</div>
			{/each}
		</div>
		<p>Sorted Array: [{sorted}]</p>
		<button on:click|preventDefault={selectionSort} class="highlighted-green"> Run </button>
		<button on:click={reset} class="highlighted-red">Reset</button>
	</div>
</div>

<style>
	.container {
		width: auto;
		height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		background-color: antiquewhite;
	}

	.card {
		width: 80%;
		padding: 1rem;
		display: flex;
		align-items: center;
		border-radius: 0.5rem;
		flex-direction: column;
		justify-content: center;
		background-color: azure;
	}

	.array {
		gap: 0.5rem;
		display: flex;
		margin: 1rem 0;
		flex-direction: row;
	}

	.item {
		border-radius: 0.5rem;
		padding: 0.25rem 0.5rem;
		border: 2px solid black;
	}

	.highlighted-green {
		color: #479e21;
		background-color: #beedaa;
	}

	.highlighted-red {
		color: #a91842;
		background-color: #e43f6f;
	}

	button {
		margin: 0.25rem 0;
		padding: 0.5rem 1rem;
		border-radius: 0.5rem;
	}
</style>
