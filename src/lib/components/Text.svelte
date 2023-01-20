<script lang="ts">
	type Tag = 'h1' | 'h2' | 'h3' | 'h4' | 'h5' | 'h6' | 'p' | 'span' | 'div';
	type Design = 'h1' | 'h2' | 'h3' | 'h4' | 'h5' | 'h6' | 'body' | 'outline';

	export let tag: Tag = 'div';
	export let design: Design = 'body';

	const classList = `text ${design || ''}`;
</script>

{#if tag === 'h1'}
	<h1 class={classList}><slot /></h1>
{:else if tag === 'h2'}
	<h2 class={classList}><slot /></h2>
{:else if tag === 'h3'}
	<h3 class={classList}><slot /></h3>
{:else if tag === 'h4'}
	<h4 class={classList}><slot /></h4>
{:else if tag === 'h5'}
	<h5 class={classList}><slot /></h5>
{:else if tag === 'h6'}
	<h6 class={classList}><slot /></h6>
{:else if tag === 'p'}
	<p class={classList}><slot /></p>
{:else if tag === 'span'}
	<span class={classList}><slot /></span>
{:else}
	<div class={classList}><slot /></div>
{/if}

<style>
	.text {
		font-size: var(--ad-sys-typescale-body-small-size);
		line-height: var(--ad-sys-typescale-body-small-line-height);
		font-weight: var(--ad-sys-typescale-body-small-weight);
	}

	@media screen and (max-height: 900px) {
		.text {
			font-size: var(--ad-sys-typescale-body-medium-size);
			line-height: var(--ad-sys-typescale-body-medium-line-height);
			font-weight: var(--ad-sys-typescale-body-medium-weight);
		}
	}

	@media screen and (max-height: 1360px) {
		.text {
			font-size: var(--ad-sys-typescale-body-large-size);
			line-height: var(--ad-sys-typescale-body-large-line-height);
			font-weight: var(--ad-sys-typescale-body-large-weight);
		}
	}

	@media screen and (max-height: 1440px) {
		.text {
			font-size: var(--ad-sys-typescale-body-large-size);
			line-height: var(--ad-sys-typescale-body-large-line-height);
			font-weight: var(--ad-sys-typescale-body-large-weight);
		}
	}

	@media screen and (max-height: 1440px) {
		.text {
			font-size: var(--ad-sys-typescale-display-medium-size);
			line-height: var(--ad-sys-typescale-display-medium-line-height);
			font-weight: var(--ad-sys-typescale-display-medium-weight);
		}
	}

	@media screen and (max-height: 2560px) {
		.text {
			font-size: var(--ad-sys-typescale-display-large-size);
			line-height: var(--ad-sys-typescale-display-large-line-height);
			font-weight: var(--ad-sys-typescale-display-large-weight);
		}
	}
</style>
