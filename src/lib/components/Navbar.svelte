<script lang="ts">
	export let variant: 'light' | 'dark' = 'light';
</script>

<header class={variant === 'dark' ? 'bg-nav-dark' : 'bg-nav-light'}>
	<nav class="navbar-info-wrap">
		<!-- Left -->
		<div class="navbar-links-wrap">
			<a href="/" class="link-img-polo-desk">
				<img src="/poloLogoNavDesk.png" alt="Polo" class="img-polo-nav-desk" />
			</a>

			<a href="/precios" class="navbar-link">Precios</a>
			<a href="/polomini" class="navbar-link">PoloMini</a>

			<!-- El dropdown de Funcionalidades -->
			<div class="dropdown">
				<button type="button" class="dropdown-trigger-btn navbar-link">
					Funcionalidades
					<i class="icon-fa-12 fa-solid fa-chevron-down"></i>
				</button>

				<div class="dropdown-menu">
					<a href="/inventarios" class="dropdown-item">Inventarios</a>
					<a href="/delivery" class="dropdown-item">Delivery</a>
				</div>
			</div>
			<a href="/vendePolotab" class="navbar-link">Vende PoloTab</a>
		</div>

		<!-- Right -->
		<div class="navbar-links-wrap">
            <a href="/TODOP" class="navbar-link">Soporte</a>
            <a href="/TODOP" class="navbar-link">Portal</a>
            <a href="/TODOP" class="navbar-link">Empieza con PoloTab</a>

		</div>
	</nav>
</header>

<style>
	/* Voy a tener los diseños de ambas nav y cada quien la llama y coloca la variante que el quiere */
	header {
		backdrop-filter: blur(12px);
		display: flex;
		height: 70px;
		padding: 0 39px;
		align-self: stretch;
	}

	.navbar-info-wrap {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		max-width: 1800px;
	}

	header.bg-nav-dark {
		border-bottom: 1px solid rgba(0, 0, 0, 0.1);
		background: rgba(13, 13, 13, 0.8);
		color: rgba(255, 255, 255, 0.2);
	}

	header.bg-nav-light {
		border-bottom: 1px solid rgba(255, 255, 255, 0.1);
		background: rgba(250, 250, 250, 0.8);
		color: rgba(0, 0, 0, 0.2);
	}

	.navbar-links-wrap {
		display: flex;
		flex-direction: row;
		align-items: center;
		gap: 20px;
	}

	.img-polo-nav-desk {
		height: 20px;
		transition:
			transform 0.2s ease,
			opacity 0.2s ease;
	}

	.link-img-polo-desk:hover .img-polo-nav-desk {
		transform: scale(1.03);
		opacity: 0.9;
	}

	.navbar-link {
		font-size: 14px;
        line-height: 14px;
		letter-spacing: 0.42px;
	}

	.dropdown-trigger-btn:hover,
	.navbar-link:hover {
		color: var(--polo-blue);
	}



	/* Dropdown hover relative */
	.dropdown {
		position: relative;
		display: inline-flex;
	}

	.dropdown-trigger-btn {
		display: inline-flex;
		gap: 5px;
		cursor: pointer;
	}

	/* Escondido */
	.dropdown-menu {
		position: absolute;
		top: calc(100% + 26px);
		display: flex;
		flex-direction: column;
		gap: 6px;
		min-width: 220px;
		padding: 12px 20px;
		border-radius: 24px;
		/* Escondido opac=0 y hidden - TODOP*/
		opacity: 0;
		visibility: hidden;
		transform: translateY(-6px);
		transition:
			opacity 150ms ease,
			transform 150ms ease,
			visibility 150ms ease;
		z-index: 50;
	}

	/* puente invisible para evitar la zona muerta del hover*/
	.dropdown::after {
		content: '';
		position: absolute;
		left: 0;
		right: 0;
		top: 100%;
		height: 26px; /* MISMO valor que tu gap */
	}

	/* Muestro con hover a .dropdown */
	.dropdown:hover .dropdown-menu {
		opacity: 1;
		visibility: visible;
		transform: translateY(0);
	}

	.dropdown-item {
		text-decoration: none;
		color: inherit;
	}

	/* Theme the menu based on the navbar variant */
	header.bg-nav-dark .dropdown-menu {
		background: rgba(13, 13, 13, 0.8);
		border-color: rgba(255, 255, 255, 0.12);
		color: rgba(255, 255, 255, 0.2);
		backdrop-filter: blur(12px);
	}

	header.bg-nav-light .dropdown-item:hover,
	header.bg-nav-dark .dropdown-item:hover {
		color: var(--polo-blue);
	}

	header.bg-nav-light .dropdown-menu {
		background: rgba(250, 250, 250, 0.92);
		border-color: rgba(0, 0, 0, 0.1);
		color: rgba(0, 0, 0, 0.2);
		border-color: rgba(238, 238, 238, 0.8);
		border-width: 1px;
	}
</style>
