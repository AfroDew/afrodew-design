<script lang="ts">
	import { text } from 'svelte/internal';

	// type Tag = 'input';
	type Design = 'modern' | 'classic';
	type Type =
		| 'button'
		| 'checkbox'
		| 'color'
		| 'date'
		| 'datetime-local'
		| 'email'
		| 'file'
		| 'hidden'
		| 'image'
		| 'long-text'
		| 'month'
		| 'number'
		| 'password'
		| 'radio'
		| 'range'
		| 'reset'
		| 'search'
		| 'submit'
		| 'tel'
		| 'text'
		| 'time'
		| 'url'
		| 'week'
		| (string & {});

	// export let tag: Tag = 'input';
	export let type: Type = 'text';
	export let design: Design = 'modern';
	export let label: string | undefined = undefined;
	export let placeholder: string | undefined = undefined;
	export let value: any = '';

	const classList = ['input', design ? `design-${design}` : ''].join(' ');
</script>

<div class={classList}>
	<!-- Label -->
	{#if label}
		<label for="">{label}</label>
	{/if}

	<div class="control">
		<slot name="pre" />

		<!-- Control -->
		{#if type === 'long-text'}
			<textarea {value} {placeholder} />
		{:else}
			<input {value} {type} {placeholder} />
		{/if}

		<slot name="post" />
	</div>
</div>

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
