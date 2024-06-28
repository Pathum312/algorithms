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
	 * Bubble sort algo thats highlights and shows the way the values are analyzed.
	 */
	const bubbleSort = async () => {
		let swapped;

		do {
			swapped = false;
			for (let i = 0; i < unsorted.length - 1; i++) {
				// Remove any previous highlighting
				reset();
				// Highlights the first value and all other values its being compared too.
				highlight(HighlightType.COMPARE, i, i + 1);
				// Adds a 1 second delay
				await new Promise(resolve => setTimeout(resolve, 1000));
				if (unsorted[i] > unsorted[i + 1]) {
					// Remove any previous highlighting
					reset();
					// Highlights the first value and all other values its being compared too.
					highlight(HighlightType.SWAP_SELECTED, i, i + 1);
					// Adds a 1 second delay
					await new Promise(resolve => setTimeout(resolve, 1000));
					[unsorted[i], unsorted[i + 1]] = [unsorted[i + 1], unsorted[i]];
					// Remove any previous highlighting
					reset();
					// Highlights the first value and all other values its being compared too.
					highlight(HighlightType.SWAP_FINISHED, i, i + 1);
					// Adds a 1 second delay
					await new Promise(resolve => setTimeout(resolve, 1000));
					swapped = true;
				}
			}
		} while (swapped);
	};
</script>

<Algorithm>
	<Array array={unsorted} {compare} {swapping} {swapped} />
	<ButtonCard>
		<Button on:click={() => reset('ALL')}>Reset</Button>
		<Button on:click={bubbleSort}>Sort</Button>
	</ButtonCard>
</Algorithm>
