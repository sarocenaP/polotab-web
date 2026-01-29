<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.png';
	import Navbar from '$lib/components/Navbar.svelte';
	import '../estilos.css';


	//let { children } = $props();
	
</script>

<!-- <Navbar/> -->
  
<main>
	<slot />
	<!-- el slot es la renderizacion de la pagina actual. ejemplo /precios -->
	
</main>

<!-- <svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()} -->
