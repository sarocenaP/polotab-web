<script lang="ts">
	export let current = '';
	export let variant: 'light' | 'dark' = 'light';
</script>

<nav aria-label="Breadcrumb" class="mb-8">
	<ol class="breadcrumb-list">
		<!-- Link imagen y texto juntos-->
		<li class="home-img-link">
			<a href="/" class="home-link-wrap">
				<img src="/breadcrumbImg.png" alt="Polo small logo" class="bread-img" />

				<span class="bread-txt">PoloTab</span>
			</a>
		</li>

		<!-- icono separador  -->
		<i class={`fa-solid fa-chevron-right ${variant === 'dark' ? 'icon-dark' : 'icon-light'}`}></i>

		<!-- Current page -->
		<li class="bread-txt">
			{current}
		</li>
	</ol>
</nav>

<style>
	.breadcrumb-list,
	.home-link-wrap {
		display: flex;
		flex-direction: row;
		gap: 12px;
		align-items: center;
	}

	.bread-img {
		width: 14px;
		padding-bottom: 2px;
	}

	.bread-txt {
		color: var(--polo-blue);
		font-size: 18px;
		line-height: 24px;
		letter-spacing: 0.54px;
	}

	i {
		font-size: 14px;
		line-height: 24px;
	}

	i.icon-dark {
		color: #fff;
		opacity: 0.4;
	}

	i.icon-light {
		color: #000;
		opacity: 0.4;
	}
</style>
