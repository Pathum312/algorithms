<script lang="ts">
	import { Algorithm, Array, ButtonCard, Button } from '$lib/components/ui';

	$: unsorted = [64, 34, 25, 12, 22, 90, 11];
	$: compare = { firstIndex: -1, secondIndex: -1 };
	$: swapping = { firstIndex: -1, secondIndex: -1 };
	$: swapped = { firstIndex: -1, secondIndex: -1 };

	/**
	 * Reset the values used to highlight the values in the array.
	 * @param type? - 'ALL' for resetting everything
	 */
	const reset = (type?: string) => {
		compare['firstIndex'] = -1;
		compare['secondIndex'] = -1;
		swapping['firstIndex'] = -1;
		swapping['secondIndex'] = -1;
		swapped['firstIndex'] = -1;
		swapped['secondIndex'] = -1;
		if (type === 'ALL') unsorted = [64, 34, 25, 12, 22, 90, 11];
	};

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
				compare['firstIndex'] = firstIndex;
				compare['secondIndex'] = secondIndex;
				break;
			case HighlightType.SWAP_SELECTED:
				swapping['firstIndex'] = firstIndex;
				swapping['secondIndex'] = secondIndex;
				break;
			case HighlightType.SWAP_FINISHED:
				swapped['firstIndex'] = firstIndex;
				swapped['secondIndex'] = secondIndex;
				break;
			default:
				break;
		}
	};

	/**
	 * Injection sort algo thats highlights and shows the way the values are analyzed.
	 */
	const injectionSort = async () => {
		for (let i = 1; i < unsorted.length; i++) {
			let current = unsorted[i];
			let j = i - 1;

			// Remove any previous highlighting
			reset();
			// Highlights the first value and all other values its being compared too.
			highlight(HighlightType.SWAP_SELECTED, i, j);
			// Adds a 1 second delay
			await new Promise(resolve => setTimeout(resolve, 1000));

			while (j >= 0 && unsorted[j] > current) {
				unsorted[j + 1] = unsorted[j];

				// Remove any previous highlighting
				reset();
				// Highlights the first value and all other values its being compared too.
				highlight(HighlightType.SWAP_FINISHED, j + 1, j + 1);
				// Adds a 1 second delay
				await new Promise(resolve => setTimeout(resolve, 1000));

				j--;

				// Remove any previous highlighting
				reset();
				// Highlights the first value and all other values its being compared too.
				highlight(HighlightType.SWAP_SELECTED, j, j);
				// Adds a 1 second delay
				await new Promise(resolve => setTimeout(resolve, 1000));
			}

			unsorted[j + 1] = current;

			// Remove any previous highlighting
			reset();
			// Highlights the first value and all other values its being compared too.
			highlight(HighlightType.SWAP_FINISHED, j + 1, j + 1);
			// Adds a 1 second delay
			await new Promise(resolve => setTimeout(resolve, 1000));
		}
	};
</script>

<Algorithm>
	<Array array={unsorted} {compare} {swapping} {swapped} />
	<ButtonCard>
		<Button on:click={() => reset('ALL')}>Reset</Button>
		<Button on:click={injectionSort}>Sort</Button>
	</ButtonCard>
</Algorithm>
