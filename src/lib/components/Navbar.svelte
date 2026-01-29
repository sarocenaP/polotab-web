<script lang="ts">
	export let variant: 'white' | 'red' = 'white';
	let open = false;
</script>

<header class={variant === 'red' ? 'bg-red' : 'bg-blue'}>
	<nav class="mx-auto flex max-w-6xl items-center justify-between px-6 py-4">
		<!-- Left -->
		<div class="flex items-center gap-8">
			<a href="/" class="flex items-center gap-2 font-semibold">
				<img src="/logo.svg" alt="PoloTab" class="h-6 w-auto" />
			</a>

			<div class="flex items-center gap-6 text-sm text-neutral-700">
				<a href="/precios" class="hover:text-neutral-950">Precios</a>
				<a href="/polomini" class="hover:text-neutral-950">PoloMini</a>

				<!-- El dropdown de Funcionalidades -->
				<div class="relative">
					<button
						type="button"
						class="flex items-center gap-1 hover:text-neutral-950"
						on:click={() => (open = !open)}
					>
						Funcionalidades
						<span class="text-xs">▾</span>
					</button>

					{#if open}
						<div
							class="absolute top-full left-0 mt-2 w-56 rounded-lg border bg-white p-2 shadow-sm"
						>
							<a href="/inventarios" class="block rounded-md px-3 py-2 text-sm hover:bg-blue-100">
								Inventarios
							</a>
							<a href="/delivery" class="block rounded-md px-3 py-2 text-sm hover:bg-neutral-100">
								Delivery
							</a>
						</div>
					{/if}
				</div>

				<a href="/vendePolotab" class="hover:text-neutral-950">Vende PoloTab</a>
			</div>
		</div>

		<!-- Right -->
		<div class="flex items-center gap-6 text-sm">
			<span class="text-neutral-700">Soporte</span>
			<span class="text-neutral-700">Portal</span>
			<span class="rounded-md bg-blue-600 px-3 py-2 font-medium text-white">
				Empieza con PoloTab
			</span>
		</div>
	</nav>
</header>

<style>
	header.bg-red {
		background: #dc2626;
		color: white;
	}

	header.bg-blue {
		background: blue;
		color: #111827;
	}
</style>
