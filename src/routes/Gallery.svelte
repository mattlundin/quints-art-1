<script>
	import { onMount } from 'svelte';
	// import { gsap } from 'gsap';
	// import { ScrollTrigger } from 'gsap/dist/ScrollTrigger.min.js';
	// gsap.registerPlugin(ScrollTrigger);

	import { gsap, ScrollTrigger } from '../gsap';

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);

		gsap.from('.gallery-header', {
			opacity: 0,
			y: -300,
			x: 200,
			rotate: -180,
			duration: 1
		});

		// gsap.utils.toArray('.art-work').forEach((el) => {
		// 	gsap.from(el, {
		// 		opacity: 0,
		// 		scale: 0.005,
		// 		duration: 1.3,
		// 		scrollTrigger: {
		// 			trigger: el,
		// 			start: 'bottom 80%',
		// 			reverse: true,
		// 			toggleActions: 'play none none reverse'
		// 		}
		// 	});
		// });

		const artWorks = gsap.utils.toArray('.art-work');
		for (let i = 0; i < artWorks.length; i++) {
			let artWork = artWorks[i];

			// ScrollTrigger.matchMedia({
			// 	// laptop and smaller
			// 	'(max-height: 600px)': function () {
			// 		gsap.to(artWork, {
			// 			scrollTrigger: {
			// 				trigger: artWork,
			// 				start: 'bottom 95%',
			// 				reverse: true,
			// 				toggleActions: 'play none none reverse'
			// 			},
			// 			opacity: 1,
			// 			scale: 1,
			// 			duration: 0.8
			// 		});
			// 	}
			// });

			// ScrollTrigger.matchMedia({
			// 	// bigger
			// 	'(min-height: 600px)': function () {
			ScrollTrigger.refresh();

			gsap.to(artWork, {
				scrollTrigger: {
					trigger: artWork,
					start: 'bottom 90%',
					reverse: true,
					toggleActions: 'play none none reverse'
				},
				opacity: 1,
				scale: 1,
				duration: 0.8
			});
		}
	});
	// 	}
	// });

	ScrollTrigger.refresh();
</script>

<svelte:head>
	<title>Gallery</title>
</svelte:head>

<div
	class="main bg-yellow-50 h-auto z-10 bg-no-repeat bg-auto bg-center bg-fixed overflow-auto"
	style="background-image: url('images/blue-splatter.png');
  background-size: 800px 500px;
"
>
	<div class="header flex flex-col items-center mb-48 pt-24 text-gray-200">
		<h2 class="gallery-header mt-3 xs:text-8xl md:text-9xl text-6xl text-shadow-lg shadow-black">
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
		class="img-container grid sm:grid-cols-2 lg:grid-cols-3 lg:mx-auto h-auto grid-cols-1 gap-8 justify-center max-w-screen-2xl mx-auto px-4 pb-24"
	>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-1.webp" alt="" title="painting1" />
		</div>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-2.webp" alt="" title="painting2" />
		</div>
		<div class="art-work opacity-0 scale-50 h-fit w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-3.webp" alt="" title="painting3" class="" />
		</div>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-4.webp" alt="" title="painting4" />
		</div>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-5.webp" alt="" title="painting5" />
		</div>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-6.webp" alt="" title="painting6" />
		</div>
		<!--  -->
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black ">
			<img src="/images/painting-1.webp" alt="" title="painting1" />
		</div>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-2.webp" alt="" title="painting2" />
		</div>
		<div class="art-work opacity-0 scale-50 h-fit w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-3.webp" alt="" title="painting3" class="" />
		</div>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-4.webp" alt="" title="painting4" />
		</div>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-5.webp" alt="" title="painting5" />
		</div>
		<div class="art-work opacity-0 scale-50 w-full cursor-pointer shadow-2xl shadow-black">
			<img src="/images/painting-6.webp" alt="" title="painting6" />
		</div>
	</section>
</div>
