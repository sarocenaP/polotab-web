<script lang="ts">
	export let className = '';
	export let tone: 'dark' | 'light' = 'dark'; // controla colores de texto/desc
</script>

<section class={`hero-duo-layout hero--${tone} ${className} cont-max`}>
	<!-- Info hero -->
	<div class="hero-left">
		<slot name="content-hero-left" />
	</div>
	<!-- media hero -->
	<div class="hero-right">
		<div class="hero-right-inner">
			<slot name="content-media-left"/>
		</div>
	</div>
</section>

<style>
	/* layout de la hero */
	.hero-duo-layout {
		display: flex;
		gap: 48px;
		align-items: center;
		padding: 72px 0;
	}

	/* si el sitio es DARK*/
	/* se definen las variables con los colores a usar */
	.hero--dark {
		--hero-desc: var(--gray-desc-blackSite);
		--hero-title: var(--text-blackSite, #fff);
	}

	/* Si el sitio es LIGHT*/
	/* se definen las variables con los colores a usar */
	.hero--light {
		--hero-desc: var(--gray-desc-WhiteSite);
		--hero-title: var(--text-whiteSite, rgba(0, 0, 0, 0.8));
	}

	/* se aplican las variables a los elementos en la hero*/
	.hero-left :global(h1) {
		color: var(--hero-title);
		font-size: 60px;
		line-height: 70px;
		letter-spacing: 1.8px;
	}

	.hero-left :global(.hero-desc) {
		color: var(--hero-desc);
		font-size: 18px;
		line-height: 24px;
		letter-spacing: 0.54px;
	}

	.hero-left :global(span) {
		color: var(--polo-blue);
	}

	/* esqueleto hrml/css */
	.hero-left,
	.hero-right {
		width: 100%;
	}

	.hero-right {
		height: 420px;
		min-width: 0;
	}

	.hero-right-inner {
		width: 100%;
		height: 100%;
	}
</style>
