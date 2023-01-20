<script lang="ts">
	type Design = 'modern' | 'classic';

	interface AddedRemoved {
		(item: string, items: string[]): void;
	}

	export let design: Design = 'modern';
	export let items: string[] = [];
	export let added: AddedRemoved | undefined = undefined;
	export let removed: AddedRemoved | undefined = undefined;

	$: innerItems = items;
	$: value = '';

	const classList = ['chips', design ? `design-${design}` : ''].join(' ');
	const handleChange = (e: any) => (value = e.target.value);
	const handleEnter = (e: any) => {
		if (e.code !== 'Enter') return;

		// Add current value to items
		innerItems = innerItems.concat([value]);

		// Notify Added
		if (added) added(value, innerItems);

		// Clear value
		value = '';
	};
	const createHandleRemove = (key: number) => () => {
		const prev = [...innerItems];

		// Remove item
		innerItems = innerItems.filter((_, k) => key !== k);

		// Notify removed
		if (removed) removed(prev[key], innerItems);
	};
</script>

<div class={classList}>
	<input type="text" bind:value on:change={handleChange} on:keydown={handleEnter} />
	<div class="items">
		{#each innerItems as item, key}
			<div class="item">
				<span>{item}</span>
				<button on:click={createHandleRemove(key)}>X</button>
			</div>
		{/each}
	</div>
</div>

<style>
	* {
		box-sizing: border-box;
	}

	/* Design */
	/* .design-modern {

	}

	.design-classic {
		
	}*/
</style>
