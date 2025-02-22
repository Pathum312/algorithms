<script lang="ts">
	$: swappedFirstIndex = -1;
	$: swappedSecondIndex = -1;
	$: swappingFirstIndex = -1;
	$: swappingSecondIndex = -1;
	$: comparingFirstIndex = -1;
	$: comparingSecondIndex = -1;
	$: unsorted = [64, 25, 12, 22, 11];

	enum HighlightType {
		COMPARE = 'COMPARE',
		SWAP_SELECTED = 'SWAP-SELECTED',
		SWAP_FINISHED = 'SWAP-FINISHED',
	}

	/**
	 * Hightlight the values being used.
	 * @param type - [COMPARE, SWAP-SELECTED, SWAP-FINISHED]
	 * @param firstIndex - Index of first value
	 * @param secondIndex - Index of second value
	 */
	const highlight = async (type: HighlightType, firstIndex: number, secondIndex: number) => {
		switch (type) {
			case HighlightType.COMPARE:
				comparingFirstIndex = firstIndex;
				comparingSecondIndex = secondIndex;
				break;
			case HighlightType.SWAP_SELECTED:
				swappingFirstIndex = firstIndex;
				swappingSecondIndex = secondIndex;
				break;
			case HighlightType.SWAP_FINISHED:
				swappedFirstIndex = firstIndex;
				swappedSecondIndex = secondIndex;
				break;
			default:
				break;
		}
	};

	/**
	 * Reset the values used to highlight the values in the array.
	 * @param type? - 'ALL' for resetting everything
	 */
	const reset = (type?: string) => {
		swappedFirstIndex = -1;
		swappedSecondIndex = -1;
		swappingFirstIndex = -1;
		swappingSecondIndex = -1;
		comparingFirstIndex = -1;
		comparingSecondIndex = -1;
		if (type === 'ALL') unsorted = [64, 25, 12, 22, 11];
	};

	/**
	 * Selection sort algo thats highlights and shows the way the values are analyzed.
	 */
	const selectionSort = async () => {
		let min_idx, i, j;

		for (i = 0; i < unsorted.length; i++) {
			min_idx = i;
			for (j = i + 1; j < unsorted.length; j++) {
				// Remove any previous highlighting
				reset();
				// Highlights the first value and all other values its being compared too.
				highlight(HighlightType.COMPARE, i, j);
				// Adds a 1 second delay
				await new Promise(resolve => setTimeout(resolve, 1000));
				if (unsorted[j] < unsorted[min_idx]) min_idx = j;
			}
			// Remove any previous highlighting
			reset();
			// Highlights the first value and second value it is going to be swapped with.
			highlight(HighlightType.SWAP_SELECTED, i, min_idx);
			// Adds a 1 second delay
			await new Promise(resolve => setTimeout(resolve, 1000));
			if (min_idx !== i) {
				[unsorted[min_idx], unsorted[i]] = [unsorted[i], unsorted[min_idx]];
				// Remove any previous highlighting
				reset();
				// Highlights the first value and second value it was swapped with.
				highlight(HighlightType.SWAP_FINISHED, i, min_idx);
				// Adds a 1 second delay
				await new Promise(resolve => setTimeout(resolve, 1000));
			} else {
				// Remove any previous highlighting
				reset();
				// Highlights a single value as both indexes are of the same value.
				highlight(HighlightType.SWAP_FINISHED, i, min_idx);
				// Adds a 1 second delay
				await new Promise(resolve => setTimeout(resolve, 1000));
			}
		}
	};
</script>

<div class="container">
	<div class="card">
		<div class="array">
			{#each unsorted as item, index}
				<div
					class="item"
					class:highlighted-red={index === comparingFirstIndex || index === comparingSecondIndex}
					class:highlighted-yellow={index === swappingFirstIndex || index === swappingSecondIndex}
					class:highlighted-green={index === swappedFirstIndex || index === swappedSecondIndex}
				>
					{item}
				</div>
			{/each}
		</div>
		<div class="buttons">
			<button on:click|preventDefault={() => reset('ALL')} class="highlighted-red">Reset</button>
			<button on:click|preventDefault={selectionSort} class="highlighted-green">Sort</button>
		</div>
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

	.highlighted-yellow {
		color: #c3a700;
		background-color: #ffee88;
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
