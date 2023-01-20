<script lang="ts">
	// type Tag = 'input';
	type Design = 'modern' | 'classic';

	// export let tag: Tag = 'input';
	export let design: Design = 'modern';
	export let fullscreen: boolean = false;
	export let open: boolean = false;
	export let closed = () => {};

	$: isOpen = open;
	$: !isOpen && closed();

	const classList = ['dialog', design ? `design-${design}` : ''].join(' ');
	const close = () => (isOpen = false);
</script>

<svelte:window
	on:keydown={(e) => {
		if (e.code !== 'Escape') return;
		isOpen = false;
	}}
/>

{#if isOpen}
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<div on:click|stopPropagation|preventDefault={close} class={classList}>
		<div on:click|stopPropagation={() => {}} class="content" class:fullscreen>
			<div class="head">
				<slot name="head" />
			</div>
			<div class="body">
				<slot />
			</div>
			<div class="footer">
				<slot name="footer" />
			</div>
		</div>
	</div>
{/if}

<style>
	* {
		box-sizing: border-box;
	}

	.dialog {
		content: '';
		position: fixed;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
		background: rgba(0, 0, 0, 0.66);
		backdrop-filter: blur(8px);
		z-index: 9999999;
		display: grid;
		place-content: center;
	}

	.content {
		max-width: 100vw;
		max-height: 100vh;
		width: 40rem;
		min-height: 20rem;
		background-color: #fff;
		display: flex;
		flex-direction: column;
		border-radius: 6px 6px 8px 8px;
		box-shadow: 0 19px 38px rgb(0 0 0 / 30%), 0 15px 12px rgb(0 0 0 / 22%);
		overflow: hidden;
	}

	.body,
	.head,
	.footer {
		padding: 1rem;
	}

	.body {
		flex-grow: 1;
	}

	.head,
	.footer {
		height: 4rem;
		overflow: hidden;
	}

	.head {
		border-bottom: 1px solid rgba(0, 0, 0, 0.05);
	}

	.footer {
		border-top: 1px solid rgba(0, 0, 0, 0.05);
	}

	.fullscreen {
		width: 100vw;
		height: 100vh;
		border-radius: 0;
	}

	/* Design */
	/* .design-plain {

	}

	.design-elevated {
		
	}

	.design-filled {
		
	} */
</style>
