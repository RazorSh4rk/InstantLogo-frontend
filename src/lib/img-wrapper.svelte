<script>
	import { Badge, Button, Card, Indicator, Spinner } from 'flowbite-svelte';
	import { AnnotationOutline, DownloadOutline } from 'flowbite-svelte-icons';
	import placeholder from '$lib/assets/placeholder.jpg';

	export let imSrc;

	const download = () => {
		console.log(imSrc);
	};
</script>

<Card img={imSrc ? imSrc : ''}>
	{#if imSrc}
		<Button on:click={download} class="nobg">
			<DownloadOutline></DownloadOutline>
		</Button>
	{:else}
		<div class="flex flex-col items-center pb-4">
			<Spinner size="12"></Spinner>
			<p>Generating this image</p>
		</div>
	{/if}
</Card>

<style>
</style>
