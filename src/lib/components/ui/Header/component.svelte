<script lang="ts">
	type Alignment = 'left' | 'right' | 'center';
	
	export let align: Alignment = 'center';

	const getAlignmentClass = () => {
		const alignmentClass = {
			left: 'align-left',
			right: 'align-right',
			center: 'align-center',
		};
		return alignmentClass[align];
	};
</script>

<header class={getAlignmentClass()}>
	<slot />
</header>

<style>
	header {
		padding: 1rem;
		display: flex;
		color: var(--clr-white);
		font-size: var(--fs-heading-0);
		background-color: var(--clr-prussian-blue);
	}

	.align-center {
		align-items: center;
		justify-content: center;
	}

	.align-left {
		align-items: flex-start;
		justify-content: flex-start;
	}

	.align-right {
		align-items: flex-end;
		justify-content: flex-end;
	}
</style>
