<script>
	import { Heading, Span, Spinner } from 'flowbite-svelte';
	import ImgWrapper from '../lib/img-wrapper.svelte';
	import FormComponent from '../lib/form-component.svelte';
	import Gallery from '../lib/assets/gallery.svelte';
	import { page } from '$app/stores';
	import logo from '$lib/assets/logo.png';

	let generated = [
		'https://avatars.githubusercontent.com/u/44329147?v=4',
		'https://avatars.githubusercontent.com/u/44329147?v=4',
		undefined
	];

	let purchaseSuccess = false;

	const paymentId = $page.url.searchParams.get('paymentid');
</script>

<div class="content m-auto grid grid-cols-5 gap-4 text-white">
	<div class="hidden md:flex"></div>

	<div class="col-span-5 md:col-span-3">
		<div class="mb-8 mt-4 text-center">
			<Heading tag="h1" customSize="text-3xl font-extrabold  md:text-5xl lg:text-6xl">
				<Span gradient>LogoMKR</Span>
			</Heading>
			<p class="mt-4 text-xl">
				The simplest, easiest way to create one-off logos for your business 🏢, project 📝, stickers
				🎨, shirts 👕, anything 🤔
			</p>
			<p class="text-md mb-4 mt-4">
				✅ No subscriptions <br />
				✅ No recurring payment <br />
				✅ No ads <br />
				✅ No confusing settings that are not explained anywhere <br />
			</p>
		</div>

		<div class="grid grid-cols-5">
			<div class="col-span-5 md:col-span-2">
				<Gallery></Gallery>
			</div>
			<FormComponent></FormComponent>
		</div>

		{#if paymentId}
			{#if !purchaseSuccess}
				<div class="grid grid-cols-3">
					<p></p>
					<div class="text-center">
						<div class="grid grid-cols-3">
							<Spinner size={12}></Spinner>
							<span class="col-span-2 text-xl">Waiting for payment to process</span>
						</div>
					</div>
					<p></p>
				</div>
			{:else}
				<div class="grid grid-cols-3 gap-8">
					{#each generated as url}
						<ImgWrapper imSrc={url}></ImgWrapper>
					{/each}
				</div>
			{/if}
		{/if}
	</div>
	<div class="hidden md:flex"></div>
</div>
