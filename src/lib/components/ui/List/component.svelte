<script lang="ts">
	export let name = '';
</script>

<div class="list">
	<h4>{name}</h4>
	<ul>
		<slot />
	</ul>
</div>

<style>
    .list {
        margin: 1rem 0;
    }

	ul {
		padding: 0 1rem;
	}
</style>
