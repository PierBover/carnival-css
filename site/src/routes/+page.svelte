<script>
	import './index.scss';
	import Turbo from '$lib/components/svg/Turbo.svelte';

	const colors = ['Text', 'Primary', 'Secondary', 'Success', 'Danger'];
	const tintValues = [25, 50, 100, 200, 300, 400, 500, 600, 700, 800, 900];
	const sizes = ['mini', 'small', '', 'large', 'huge'];
	const buttonVariants = ['', 'secondary', 'success', 'danger', 'contrast'];
</script>

<h1>Carnival CSS</h1>

<h2>Colors</h2>

{#each colors as color}
	<div class="color">
		<h3>{color}</h3>
		<div class="swatches">
			{#each tintValues as value}
				<div class="swatch" style:background-color={`var(--cnv-color-${color.toLocaleLowerCase()}-${value})`}>
					{value}
				</div>
			{/each}
		</div>
	</div>
{/each}

<h2>Buttons</h2>

<div class="button-row">
	{#each sizes as size}
		<button class={`cnv ${size}`} style:margin-right='.25rem'>Button text</button>
	{/each}
</div>

{#each buttonVariants as variant}
	<div class="button-row">
		<button class={`cnv ${variant}`}>Button text</button>
		<button class={`cnv ${variant}`} disabled>Button text</button>
		<button class={`cnv ${variant} round`}>Button text</button>
		<button class={`cnv ${variant} outlined`}>Button text</button>
		<button class={`cnv ${variant} subtle`}>Button text</button>
		<button class={`cnv ${variant} text-only`}>Button text</button>
	</div>
{/each}

<div class="button-row">
	<button class="cnv with-icon"><Turbo/>Turbo</button>
	<button class="cnv with-icon" disabled><Turbo/>Turbo</button>
	<button class="cnv with-icon round"><Turbo/>Turbo</button>
	<button class="cnv with-icon outlined"><Turbo/>Turbo</button>
	<button class="cnv with-icon subtle"><Turbo/>Turbo</button>
	<button class="cnv with-icon text-only"><Turbo/>Turbo</button>
</div>
