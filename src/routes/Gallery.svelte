<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger.js';

	ScrollTrigger.refresh();

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);

		const artWork = gsap.utils.toArray('.art-work');
		for (let i = 0; i < artWork.length; i++) {
			let art = artWork[i];

			gsap.from(art, {
				scrollTrigger: {
					trigger: art,
					start: '10px, 85%'
				},
				duration: 2,
				scale: 0.001
				// opacity: 0,
				// rotation: 90
			});
		}

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
	<div class="header flex flex-col items-center mb-48 pt-24 text-gray-200">
		<h2
			class="gallery mt-3 xs:text-7xl sm:text-8xl md:text-9xl text-6xl text-shadow-lg shadow-black"
		>
			Gallery
		</h2>
	</div>

	<!-- * Overlay Example -->
	<!-- {#if $isOverlayOpen}
		<Overlay>
			<p>Coolest... Overlay... Ever...</p>
		</Overlay>
	{/if} -->

	<!-- {$isOverlayOpen}
	<button
		class="p-4 rounded-md bg-purple-900 text-purple-100 my-4"
		on:click={() => {
			isOverlayOpen.set(true);
		}}>Open Overlay</button
	> -->

	<section
		class="img-container grid sm:grid-cols-2 lg:grid-cols-3 lg:mx-auto h-auto grid-cols-1 gap-10 justify-center max-w-screen-2xl mx-auto px-2 pb-24"
	>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black ">
			<img src="/images/painting-1.webp" alt="" title="painting1" />
		</div>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-2.webp" alt="" title="painting2" />
		</div>
		<div class="art-work h-fit w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-3.webp" alt="" title="painting3" class="" />
		</div>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-4.webp" alt="" title="painting4" />
		</div>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-5.webp" alt="" title="painting5" />
		</div>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-6.webp" alt="" title="painting6" />
		</div>
		<!--  -->
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black ">
			<img src="/images/painting-1.webp" alt="" title="painting1" />
		</div>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-2.webp" alt="" title="painting2" />
		</div>
		<div class="art-work h-fit w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-3.webp" alt="" title="painting3" class="" />
		</div>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-4.webp" alt="" title="painting4" />
		</div>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-5.webp" alt="" title="painting5" />
		</div>
		<div class="art-work w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-6.webp" alt="" title="painting6" />
		</div>
	</section>
</div>
