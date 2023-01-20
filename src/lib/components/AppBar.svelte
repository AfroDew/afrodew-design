<script lang="ts">
	// type Tag = 'input';
	type Design = 'modern' | 'classic';

	// export let tag: Tag = 'input';
	export let design: Design = 'modern';
	export let fixed: boolean = false;

	const classList = ['appbar', design ? `design-${design}` : ''].join(' ');
</script>

<div class:fixed class={classList}>AppBar</div>

<style>
	.appbar {
		content: '';
		position: relative;
		top: 0;
		left: 0;
		width: 100vw;
		height: 80px;
		z-index: 9999999;
		display: grid;
		place-content: center;
		transition: background 0.6s ease;
		border-bottom: 1px solid #eaeaea;
		transform: translateZ(0);
		backdrop-filter: saturate(180%) blur(5px);
		background: hsla(0, 0%, 100%, 0.8);
	}

	.fixed {
		position: fixed;
	}

	/* Design */
	/* .design-plain {

	}

	.design-elevated {
		
	}

	.design-filled {
		
	} */
</style>
