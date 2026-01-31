<script lang="ts">
	import HeroDuoLayout from '$lib/components/heroDuoLayout/HeroDuoLayout.svelte';
	import Breadcrumb from '$lib/components/Breadcrumb.svelte';
	import Navbar from '$lib/components/Navbar.svelte';
	import ButtonsType from '$lib/components/ButtonsType.svelte';
	import HeroMedia from '$lib/components/heroDuoLayout/HeroMedia.svelte';
</script>

<svelte:head>
	<title>PoloTab | Planes y precios para cafeterías y restaurantes</title>
</svelte:head>

<main class="main-black" style="background: var(--bg-black); color: var(--txt-white);">
	<Navbar variant="dark" />

	<!-- ====================================================================================================== -->
	<!-- ============================================ SECCION HERO ============================================ -->

	<HeroDuoLayout tone="dark">
		<div slot="content-hero-left" class="hero-structure-left">
			<Breadcrumb variant="dark" current="Precios" />

			<h1>Extremadamente intuitivo, demasiado capaz y ultra seguro</h1>

			<p class="hero-desc">
				Descubre por qué nos eligen restaurantes y cafeterías en más de 36 ciudades de México.
			</p>

			<ButtonsType variant="link" href="#section-planes">
				Planes y precios <i class="icon-fa-14 fa-solid fa-arrow-down"></i>
			</ButtonsType>
		</div>

		<!-- Si todavía no tienes media, puedes dejarlo vacío o poner un placeholder -->
		<div slot="content-media-left">
			<HeroMedia
				variant="youtube"
				youtube={{
					youtubeId: 'PvhRLDxWrRQ',
					poster: '/tableSetup.jpg',
					alt: 'Video explicativo de los planes de PoloTab',
					buttonLabel: 'Cómo funciona'
				}}
			/>
		</div>
	</HeroDuoLayout>

	<!-- ====================================================================================================== -->
</main>

<style>
	.hero-structure-left {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}
</style>
