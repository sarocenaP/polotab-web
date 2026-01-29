<script>
	export let current = '';
    import favicon from '$lib/assets/favicon.png';

</script>

<nav aria-label="Breadcrumb" class="mb-8">

	<ol class="flex items-center gap-2 text-sm">
        <!-- Link imagen y texto -->
		<li class="flex items-center gap-2">
			<a href="/" class="flex items-center gap-2 hover:opacity-90">
				<img
					src={favicon}
					alt="Polo small logo"
					class="h-6 w-6 object-contain"
				/>

				<span class="font-medium text-blue-500 hover:underline">
					PoloTab
				</span>
			</a>
		</li>

		<!-- Separator -->
		<li class="text-neutral-400">
			&gt;
		</li>

		<!-- Current page -->
		<li class="font-medium text-white opacity-90">
			{current}
		</li>
	</ol>
</nav>
