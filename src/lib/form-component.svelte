<script>
	import { Button, Checkbox, Input, Label, Textarea } from 'flowbite-svelte';
	import { AnnotationOutline, CaretDownOutline, CaretUpOutline } from 'flowbite-svelte-icons';
	import FaWallet from 'svelte-icons/fa/FaWallet.svelte';
	import FaPaintBrush from 'svelte-icons/fa/FaPaintBrush.svelte';

	const colors = ['black', 'gray', 'green', 'blue', 'red', 'yellow', 'purple'];
	let selected = 0;

	const pickColor = (color) => {
		console.log(color);
	};
</script>

<div class="col-span-5 md:col-span-3 ps-2">
	<Textarea id="prompt" placeholder="Describe your business" rows="10" class="mb-4 resize-none"
	></Textarea>

	<p class="text-lg col-span-3 text-center mb-2">Dominant color of logo</p>
	<div class="mb-4 grid grid-cols-9 gap-4">
		<p></p>
		{#each colors as color, idx}
			<Button pill class="p-4" style="background-color: {color}" on:click={() => (selected = idx)}>
				{#if selected === idx}
					<CaretUpOutline></CaretUpOutline>
				{:else}
					<CaretDownOutline></CaretDownOutline>
				{/if}
			</Button>
		{/each}
		<p></p>
	</div>

	<div class="grid grid-cols-5">
		
		<p class="col-span-1"></p>
		<Button class="mb-12">3 icons: $0.99</Button>
		<p></p>
		<Button class="mb-12">12 icons: $2.99</Button>
		<p class="col-span-1"></p>
	</div>
</div>

<style>
	.icon {
		width: 1rem;
		height: 1rem;
	}
</style>
