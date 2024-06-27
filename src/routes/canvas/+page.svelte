<script lang="ts">
	import { onMount } from 'svelte';

	onMount(() => {
		const canvas = document.getElementById('main-canvas');
		// @ts-ignore
		const container = canvas.parentElement;
		// @ts-ignore
		canvas.width = container.width;
		// @ts-ignore
		canvas.height = container.height;
		// @ts-ignore
		const ctx = canvas.getContext('2d');

		ctx.fillStyle = 'black';
		ctx.fillRect(10, 20, 10, 10);
	});
</script>

<div class="container">
	<div class="card">
		<canvas id="main-canvas"></canvas>
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
		height: 5rem;
		padding: 1rem;
		display: flex;
		align-items: center;
		border-radius: 0.5rem;
		flex-direction: column;
		justify-content: center;
		background-color: azure;
	}

	#main-canvas {
		position: absolute;
		background-color: aqua;
	}
</style>
