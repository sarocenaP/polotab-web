<script>
	import Navbar from '$lib/components/Navbar.svelte';
	//import Breadcrumb from '$lib/components/Breadcrumb.svelte';
	import HeroDuoLayout from '$lib/components/heroDuoLayout/HeroDuoLayout.svelte';
	import ButtonsType from '$lib/components/ButtonsType.svelte';
	import HeroMedia from '$lib/components/heroDuoLayout/HeroMedia.svelte';
</script>

<svelte:head>
	<title>PoloTab | Software y Punto de Venta para Cafeterías y Restaurantes en México</title>
</svelte:head>

<main class="main-white" style="background: var(--bg-white); color: var(--txt-white);">
	<Navbar variant="light" />

	<HeroDuoLayout tone="light">
		<div slot="content-hero-left" class="hero-structure-left">
			<!-- <Breadcrumb variant="dark" current="Precios" /> -->
			<span>Software y Punto de Venta</span>

			<h1>El sistema que las cafeterías aman</h1>

			<p class="hero-desc">
				Descubre por qué los mejores cafés y restaurantes de México usan PoloTab
			</p>

			<ButtonsType
				variant="duo"
				primary={{ label: 'Empieza con PoloTab', href: '/' }}
				secondary={{ label: 'Contáctanos', href: '/' }}
			/>
		</div>

		<!-- Si todavía no tienes media, puedes dejarlo vacío o poner un placeholder -->
		<div slot="content-media-left">
			<HeroMedia variant="image" image={{ src:"/HeroPOS.png", alt:'PoloTab POS' }} />
		</div>
	</HeroDuoLayout>
</main>

<style>
	.hero-structure-left {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}
</style>
