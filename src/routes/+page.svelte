<svelte:head>
	<title>PoloTab | Software y Punto de Venta para Cafeterías y Restaurantes en México</title>
</svelte:head>

<script>
	import Navbar from "$lib/components/Navbar.svelte";
	import Breadcrumb from '$lib/components/Breadcrumb.svelte';

</script>

<Navbar variant="light" />


<main class="main-white">
	<div class="cont-max">
		<Breadcrumb variant="light" current="Home"/>

		<h1 class="text-4xl font-semibold tracking-tight">PoloTab</h1>
		<p class="mt-3 text-lg text-neutral-600">
			Canvas limpio. Desde acá armamos Landing, Pricing, Inventarios y Comandero.
		</p>
	</div>
</main>
