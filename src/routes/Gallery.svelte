<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger.js';

	import { isOverlayOpen } from '../stores/OverlayStore.js';
	import Overlay from '../components/Overlay.svelte';

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);

		gsap.from('.gallery', {
			opacity: 0,
			y: -300,
			x: 200,
			rotate: -180,
			duration: 1
		});
	});
</script>

<svelte:head>
	<title>Gallery</title>
</svelte:head>

<div
	class="main bg-yellow-50 h-full z-10 bg-no-repeat bg-auto bg-center bg-fixed"
	style="background-image: url('images/blue-splatter.png');
  background-size: 800px 500px;
"
>
	<div class="header flex flex-col items-center pt-24 text-gray-200">
		<h2
			class="gallery mt-3 xs:text-7xl sm:text-8xl md:text-9xl text-6xl text-shadow-lg shadow-black"
		>
			Gallery
		</h2>
	</div>

	{#if $isOverlayOpen}
		<Overlay>
			<p>Coolest... Overlay... Ever...</p>
		</Overlay>
	{/if}

	{$isOverlayOpen}
	<button
		class="p-4 rounded-md bg-purple-900 text-purple-100 my-4"
		on:click={() => {
			isOverlayOpen.set(true);
		}}>Open Overlay</button
	>

	<section
		class="grid sm:grid-cols-2 lg:grid-cols-3 lg:mx-auto grid-cols-1 gap-5 justify-center mt-32 max-w-screen-xl mx-auto px-2"
	>
		<div class="w-full">
			<img src="/images/painting-1.webp" alt="" />
		</div>
		<div class="w-full">
			<img src="/images/painting-2.webp" alt="" />
		</div>
		<div class="w-full">
			<img src="/images/painting-3.webp" alt="" class="h-auto w-full" />
		</div>
		<div class="w-full">
			<img src="/images/painting-4.webp" alt="" />
		</div>
		<div class="w-full">
			<img src="/images/painting-5.webp" alt="" />
		</div>
		<div class="w-full">
			<img src="/images/painting-6.webp" alt="" />
		</div>
		<div class="h-screen" />
	</section>
</div>
