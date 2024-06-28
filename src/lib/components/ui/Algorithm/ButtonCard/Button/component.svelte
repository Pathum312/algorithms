<button on:click|preventDefault>
	<slot />
</button>

<style>
	button {
		border: none;
		border-radius: 0.25rem;
		padding: 0.25rem 0.5rem;
		filter: var(--shadow-1);
		color: var(--clr-white-200);
		background-color: var(--clr-white);
	}
</style>
