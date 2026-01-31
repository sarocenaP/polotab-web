<script lang="ts">
	type ImageMedia = { src: string; alt: string };
	type YoutubeMedia = { youtubeId: string; poster: string; alt: string; buttonLabel?: string };

	export let variant: 'image' | 'youtube' = 'image';
	export let image: ImageMedia | undefined = undefined;
	export let youtube: YoutubeMedia | undefined = undefined;
	export let className = '';

	let isPlaying = false;
	const play = () => (isPlaying = true);
	const reset = () => (isPlaying = false);
</script>

<div class={`hero-media ${className} ${isPlaying ? 'is-playing' : ''}`}>
	{#if variant === 'image'}
		{#if image?.src}
			<!-- CAPA 1: media (SIN glass) -->
			<div class="layer layer-media">
				<img src={image.src} alt={image.alt} loading="eager" />
			</div>
		{:else}
			<div class="fallback">Falta image.src</div>
		{/if}
	{:else if youtube}
		{#if !isPlaying}
			<!-- CAPA 1: media -->
			<div class="layer layer-media">
				<img src={youtube.poster} alt={youtube.alt} loading="eager" />
			</div>

			<!-- CAPA 2: glass -->
			<div class="layer layer-glass" aria-hidden="true"></div>

			<!-- CAPA 3: ui (NO blur) -->
			<div class="layer layer-ui">
				<button class="btn play-pill" type="button" on:click={play} aria-label="Reproducir video">
					<i class="icon-fa-14 fa-solid fa-play" aria-hidden="true"></i>
					{youtube.buttonLabel ?? 'Cómo funciona'}
				</button>
			</div>
		{:else}
			<!-- CAPA 1: media -->
			<div class="layer layer-media">
				<!-- svelte-ignore element_invalid_self_closing_tag -->
				<iframe
					title="YouTube video"
					src={`https://www.youtube-nocookie.com/embed/${youtube.youtubeId}?autoplay=1&rel=0&modestbranding=1`}
					allow="autoplay; encrypted-media; picture-in-picture"
					allowfullscreen
				/>
			</div>

			<!-- si querés que el blur NO esté mientras se reproduce, lo apagamos con .is-playing -->
			<div class="layer layer-glass" aria-hidden="true"></div>

			<!-- UI arriba -->
			<div class="layer layer-ui layer-ui--topright">
				<button class="close" type="button" on:click={reset} aria-label="Cerrar video">✕</button>
			</div>
		{/if}
	{:else}
		<div class="fallback">Falta youtube config</div>
	{/if}
</div>

<style>
	.hero-media {
		width: 100%;
		height: 420px;
		border-radius: 24px;
		overflow: hidden;
		position: relative;
	}

	/* Layers */
	.layer {
		position: absolute;
		inset: 0;
	}

	.layer-media {
		z-index: 0;
	}

	/* ✅ ESTA es la capa de blur + gradiente (nunca contiene el botón) */
	.layer-glass {
		z-index: 1;
		pointer-events: none;

		background: radial-gradient(
			50% 50% at 50% 50%,
			rgba(255, 255, 255, 0.1) 0%,
			rgba(255, 255, 255, 0.06) 35%,
			rgba(255, 255, 255, 0.02) 65%,
			rgba(255, 255, 255, 0) 100%
		);
		backdrop-filter: blur(6px);
	}

	/* ✅ UI siempre arriba y limpio */
	.layer-ui {
		z-index: 2;
		display: grid;
		place-items: center;
		pointer-events: none; /* para que solo los botones capturen */
	}

	.layer-ui--topright {
		display: block;
	}

	/* Media fill */
	img,
	iframe {
		width: 100%;
		height: 100%;
		display: block;
		object-fit: cover;
		border: 0;
	}

	/* Solo el botón es clickeable */
	.play-pill {
		pointer-events: auto;
		display: inline-flex;
		gap: 10px;
		align-items: center;
		height: 40px;
		padding: 0 24px;
		border-radius: 24px;
		background: var(--polo-blue);
		color: white;
		border: 0;
		cursor: pointer;
	}

	.close {
		pointer-events: auto;
		position: absolute;
		top: 12px;
		right: 12px;
		width: 34px;
		height: 34px;
		border-radius: 999px;
		border: 0;
		cursor: pointer;
		backdrop-filter: blur(12px);
		background: rgba(0, 0, 0, 0.45);
		color: white;
		font-size: 16px;
		line-height: 1;
	}

	/* Opcional: cuando está reproduciendo, apagar el glass para que el video quede limpio */
	.hero-media.is-playing .layer-glass {
		background: transparent;
		backdrop-filter: none;
	}

	.fallback {
		width: 100%;
		height: 100%;
		display: grid;
		place-items: center;
		opacity: 0.65;
		border: 1px dashed rgba(255, 255, 255, 0.2);
	}
</style>
