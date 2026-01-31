<script lang="ts">
	type ButtonsElements = {
		label: string;
		href: string;
	};

	export let variant: 'link' | 'duo' = 'link';

	// para link
	export let href: string | undefined = undefined;

	// para duo
	export let primary: ButtonsElements | undefined = undefined;
	export let secondary: ButtonsElements | undefined = undefined;
</script>

{#if variant === 'link'}
	<div class="buttons-wrap">
		<a class="btn-link" {href}>
			<slot />
		</a>
	</div>
{:else if variant === 'duo'}
	<div class="buttons-wrap buttons-wrap-duo">
		{#if primary}
			<a class="btn btn-primary" href={primary.href}>
				{primary.label}
			</a>
		{/if}

		{#if secondary}
			<a class="btn btn-secondary" href={secondary.href}>
				{secondary.label}
			</a>
		{/if}
	</div>
{/if}

<style>
	/* wrapper de el/los botones */
	.buttons-wrap {
		display: flex;
		align-items: center;
		padding-top: 22px;
	}

	.buttons-wrap-duo {
		gap: 6px;
		flex-wrap: wrap;
	}

	/* button tipo link */
	.btn-link {
		display: flex;
		flex-direction: row;
		gap: 6px;
		align-items: center;
		font-size: 18px;
		line-height: 24px; /* 133.333% */
		letter-spacing: 0.54px;
		color: var(--polo-blue);
		text-decoration: none;
	}

	/* primary button blue*/
	.btn-primary {
		background: var(--polo-blue);
		color: white;
	}

	/* secondary button transparent */
	.btn-secondary {
		background: transparent;
		color: var(--polo-blue);
		border: 2px solid var(--polo-blue);
	}
</style>
