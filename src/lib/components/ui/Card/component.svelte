<script lang="ts">
	export let title = '';
	export let description = '';
</script>

<div class="card">
	<h3>{title}</h3>
	<p class="description">{description}</p>
</div>

<style>
	.card {
		padding: 1rem;
		margin: 1rem 0;
		border-radius: 0.5rem;
		filter: var(--shadow-3);
		color: var(--clr-white-200);
		background-color: var(--clr-white);
	}

	.description {
		max-width: 70ch;
	}
</style>
