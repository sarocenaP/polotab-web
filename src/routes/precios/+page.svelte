<script>
	import Navbar from '$lib/components/Navbar.svelte';
	import Breadcrumb from '$lib/components/Breadcrumb.svelte';
</script>

<svelte:head>
	<title>PoloTab | Planes y precios</title>
</svelte:head>

<Navbar variant="dark" />

<main class="main-black" style="background: var(--bg-black); color: var(--text-white);">
	<div class="cont-max">
		<div class="hero-planes">
			<Breadcrumb variant="dark" current="Precios" />
			<h1>Extremadamente intuitivo, demasiado capaz y ultra seguro</h1>
			<p class="desc-polo-black">
				Descubre por qué nos eligen restaurantes y cafeterías en más de 36 ciudades de México.
			</p>
		</div>
	</div>
</main>

<style>
	.hero-planes {
		display: flex;
		flex-direction: column;
	}
	.desc-polo-black {
		color: var(--txt-gray-desc);
		opacity: 0.6;
	}
</style>
