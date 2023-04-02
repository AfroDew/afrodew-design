<script lang="ts">
	type Tag = 'button' | 'a' | 'div';
	type Outline = 'plain' | 'gradient' | undefined;
	type Design = 'plain' | 'elevated' | 'filled';

	export let tag: Tag = 'div';
	export let design: Design = 'plain';
	export let href: string | undefined = undefined;
	export let outline: Outline = undefined;

	const classList = [
		'button',
		design ? `design-${design}` : '',
		outline ? `outline-${outline}` : ''
	].join(' ');

	// Error reporting
	if (tag === 'a' && !href) console.warn('Tag of `a` should have an `href`.');
</script>

{#if tag === 'div'}
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<div on:click class={classList} {...$$restProps}>
		<slot name="pre" />
		<slot />
		<slot name="post" />
	</div>
{:else if tag === 'a'}
	<a on:click {href} class={classList} {...$$restProps}>
		<slot name="pre" />
		<slot />
		<slot name="post" />
	</a>
{:else}
	<button on:click class={classList} {...$$restProps}>
		<slot name="pre" />
		<slot />
		<slot name="post" />
	</button>
{/if}

<style>
	.button {
		font: 1rem;
		cursor: pointer;
		display: inline-block;
	}

	.button:not(:last-child) {
		margin-right: 0.5rem;
	}

	a.button {
		text-decoration: none;
	}

	/* Design */
	/* .design-plain {

	}

	.design-elevated {
		
	}

	.design-filled {
		
	} */

	/* Outline */
	.outline-plain {
		border: 1px solid;
	}

	.outline-gradient {
		border: 1px solid;
	}
</style>
