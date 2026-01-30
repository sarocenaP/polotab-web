<script>
	import Navbar from "$lib/components/Navbar.svelte";
	import Breadcrumb from "$lib/components/Breadcrumb.svelte";
</script>

<svelte:head>
	<title>PoloMini – PoloTab</title>
</svelte:head>

<Navbar variant="dark" />

<main class="main-black" style="background: var(--bg-black); color: var(--text-white);">

    <div class="cont-max">
        <div class="">
            <Breadcrumb variant="dark" current="PoloMini"/>
            <h1>PoloMini Comandero</h1>
            <p class="desc-polo-black">Descubre por qué nos eligen restaurantes y cafeterías en más de 36 ciudades de México.
            </p>
        </div>
    </div>

</main>


<style>

.desc-polo-black {
		color: var(--txt-gray-desc);
		opacity: 0.6;
	}
</style>
