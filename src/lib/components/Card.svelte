<script lang="ts">
	export let elevated: boolean = false;

	const classList = ['card'].join(' ');
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class:elevated class={classList} {...$$restProps} on:click>
	<slot />
</div>

<style>
	.card {
		padding: 2rem;
		background-color: rgb(235, 168, 143);
	}

	.elevated {
		padding: 2rem;
		box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.16);
	}
</style>
