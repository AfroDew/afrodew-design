<slot />

<style>
	/* DESIGN TOKENS */
	:global(:root) {
		/* Refernce Tokens */
		--ad-ref-palette-primary30: #4f378b;
		--ad-ref-palette-primary40: #6750a4;
		--ad-ref-palette-primary80: #d0bcff;
		--ad-ref-palette-primary90: #eaddff;

		--ad-ref-palette-secondary30: #4a4458;
		--ad-ref-palette-secondary40: #625b71;
		--ad-ref-palette-secondary80: #ccc2dc;
		--ad-ref-palette-secondary90: #e8def8;

		--ad-ref-palette-tertiary30: #633b48;
		--ad-ref-palette-tertiary40: #7d5260;
		--ad-ref-palette-tertiary80: #efb8c8;
		--ad-ref-palette-tertiary90: #ffd8e4;

		--ad-ref-palette-neutral10: #1C1B1F;
		--ad-ref-palette-neutral99: #FFFBFE;

		--ad-ref-palette-neutral-variant30: #49454F;
		--ad-ref-palette-neutral-variant90: #E7E0EC;

		--ad-ref-palette-error30: #8C1D18;
		--ad-ref-palette-error40: #B3261E;
		--ad-ref-palette-error80: #F2B8B5;
		--ad-ref-palette-error90: #F9DEDC;

		/* Set default mode to `light` */
		color-scheme: light;

		/* System Tokens(Color) => light mode */
		--ad-sys-color-primary: var(--ad-ref-palette-primary40);
		--ad-sys-color-primary-container: var(--ad-ref-palette-primary90);

		--ad-sys-color-secondary: var(--ad-ref-palette-secondary40);
		--ad-sys-color-secondary-container: var(--ad-ref-palette-secondary90);

		--ad-sys-color-tertiary: var(--ad-ref-palette-tertiary40);
		--ad-sys-color-tertiary-container: var(--ad-ref-palette-tertiary90);

		--ad-sys-color-surface: var(--ad-ref-palette-neutral99);
		--ad-sys-color-surface-variant: var(--ad-ref-palette-neutral-variant90);

		--ad-sys-color-background: var(--ad-ref-palette-neutral99);

		--ad-sys-color-error: var(--ad-ref-palette-error40);
		--ad-sys-color-error-container: var(--ad-ref-palette-error90);

		/* Reference Typograpy Token */
		--ad-ref-typeface-brand: 'Roboto Regular';
		--ad-ref-typeface-plain: 'Roboto Medium';
		--ad-ref-typeface-weight-regular: 400;
		--ad-ref-typeface-weight-medium: 500;

		/* System Typograpy Token: Large Display */
		--ad-sys-typescale-display-large-font: var(--ad-ref-typeface-brand);
		--ad-sys-typescale-display-large-line-height: 64px;
		--ad-sys-typescale-display-large-size: 57px;
		--ad-sys-typescale-display-large-tracking: 0px;
		--ad-sys-typescale-display-large-weight: var(--ad-ref-typeface-weight-regular);
		
		/* System Typograpy Token: Medium Display */
		--ad-sys-typescale-display-medium-font: var(--ad-ref-typeface-brand);
		--ad-sys-typescale-display-medium-line-height: 52px;
		--ad-sys-typescale-display-medium-size: 45px;
		--ad-sys-typescale-display-medium-tracking: 0px;
		--ad-sys-typescale-display-medium-weight: var(--ad-ref-typeface-weight-regular);

		/* System Typograpy Token: Large Body */
		--ad-sys-typescale-body-large-font: var(--ad-ref-typeface-plain);
		--ad-sys-typescale-body-large-line-height: 24px;
		--ad-sys-typescale-body-large-size: 16px;
		--ad-sys-typescale-body-large-tracking: 0.5px;
		--ad-sys-typescale-body-large-weight: var(--ad-ref-typeface-weight-regular);
		
		/* System Typograpy Token: Mediun Body */
		--ad-sys-typescale-body-medium-font: var(--ad-ref-typeface-plain);
		--ad-sys-typescale-body-medium-line-height: 20px;
		--ad-sys-typescale-body-medium-size: 14px;
		--ad-sys-typescale-body-medium-tracking: 0.25px;
		--ad-sys-typescale-body-medium-weight: var(--ad-ref-typeface-weight-regular);

		/* System Typograpy Token: Small Body */
		--ad-sys-typescale-body-small-font: var(--ad-ref-typeface-plain);
		--ad-sys-typescale-body-small-line-height: 16px;
		--ad-sys-typescale-body-small-size: 12px;
		--ad-sys-typescale-body-small-tracking: 0.4px;
		--ad-sys-typescale-body-small-weight: var(--ad-ref-typeface-weight-regular);
		
	}

	@media (prefers-color-scheme: dark) {
		:global(:root) {
			color-scheme: dark;

			/* System Tokens(Color) => dark mode */
			--ad-sys-color-primary: var(--ad-ref-palette-primary80);
			--ad-sys-color-primary-container: var(--ad-ref-palette-primary30);

			--ad-sys-color-secondary: var(--ad-ref-palette-secondary80);
			--ad-sys-color-secondary-container: var(--ad-ref-palette-secondary30);

			--ad-sys-color-tertiary: var(--ad-ref-palette-tertiary80);
			--ad-sys-color-tertiary-container: var(--ad-ref-palette-tertiary30);

			--ad-sys-color-surface: var(--ad-ref-palette-neutral10);
			--ad-sys-color-surface-variant: var(--ad-ref-palette-neutral-variant30);

			--ad-sys-color-background: var(--ad-ref-palette-neutral10);

			--ad-sys-color-error: var(--ad-ref-palette-error80);
			--ad-sys-color-error-container: var(--ad-ref-palette-error30);
		}
	}

	:global([color-scheme='light']) {
		color-scheme: light;

		/* System Tokens(Color) => light mode */
		--ad-sys-color-primary: var(--ad-ref-palette-primary40);
		--ad-sys-color-primary-container: var(--ad-ref-palette-primary90);

		--ad-sys-color-secondary: var(--ad-ref-palette-secondary40);
		--ad-sys-color-secondary-container: var(--ad-ref-palette-secondary90);

		--ad-sys-color-tertiary: var(--ad-ref-palette-tertiary40);
		--ad-sys-color-tertiary-container: var(--ad-ref-palette-tertiary90);

		--ad-sys-color-surface: var(--ad-ref-palette-neutral99)
		--ad-sys-color-surface-variant: var(--ad-ref-palette-neutral-variant90)

		--ad-sys-color-background: var(--ad-ref-palette-neutral99);

		--ad-sys-color-error: var(--ad-ref-palette-error40);
		--ad-sys-color-error-container: var(--ad-ref-palette-error90);
	}

	:global([color-scheme='dark']) {
		color-scheme: dark;

		/* System Tokens(Color) => dark mode */
		--ad-sys-color-primary: var(--ad-ref-palette-primary80);
		--ad-sys-color-primary-container: var(--ad-ref-palette-primary30);

		--ad-sys-color-secondary: var(--ad-ref-palette-secondary80);
		--ad-sys-color-secondary-container: var(--ad-ref-palette-secondary30);

		--ad-sys-color-tertiary: var(--ad-ref-palette-tertiary80);
		--ad-sys-color-tertiary-container: var(--ad-ref-palette-tertiary30);

		--ad-sys-color-surface: var(--ad-ref-palette-neutral10);
		--ad-sys-color-surface-variant: var(--ad-ref-palette-neutral-variant30);

		--ad-sys-color-background: var(--ad-ref-palette-neutral10);

		--ad-sys-color-error: var(--ad-ref-palette-error80);
		--ad-sys-color-error-container: var(--ad-ref-palette-error30);
	}



	/* NORMALIZE */
	:global(*),
	:global(::before),
	:global(::after) {
		box-sizing: border-box;
		margin: 0;
	}

	:global(html) {
		background-color: var(--ad-sys-color-background);
		color: var(--ad-sys-color-secondary);
		accent-color: var(--ad-sys-color-primary);
	}

	:global(body) {
		font-family: system-ui, sans-serif;
		/* padding: var(--size-6); */
		display: grid;
		place-content: center;
		/* gap: var(--size-6); */
	}
</style>
