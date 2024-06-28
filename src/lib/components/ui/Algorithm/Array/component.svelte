<script lang="ts">
	export let array: any[];
	export let compare: { firstIndex: number; secondIndex: number };
	export let swapping: { firstIndex: number; secondIndex: number };
	export let swapped: { firstIndex: number; secondIndex: number };
</script>

<div class="array">
	{#each array as value, index}
		<div
			class="item"
			class:highlighted-red={index === compare.firstIndex || index === compare.secondIndex}
			class:highlighted-yellow={index === swapping.firstIndex || index === swapping.secondIndex}
			class:highlighted-green={index === swapped.firstIndex || index === swapped.secondIndex}
		>
			{value}
		</div>
	{/each}
</div>

<style>
	.array {
		gap: 0.5rem;
		display: flex;
		margin: 1rem 0;
		flex-direction: row;
	}

	.item {
		border-radius: 0.25rem;
		padding: 0.25rem 0.5rem;
		filter: var(--shadow-1);
		background-color: var(--clr-white);
	}

	.highlighted-green {
		color: var(--clr-green-200);
		background-color: var(--clr-green);
	}

	.highlighted-yellow {
		color: var(--clr-yellow-200);
		background-color: var(--clr-yellow);
	}

	.highlighted-red {
		color: var(--clr-red-200);
		background-color: var(--clr-red);
	}
</style>
