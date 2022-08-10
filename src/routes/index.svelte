<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger.js';
	// import { CustomEase } from '../../CustomEase.min.js';

	import Header from '../components/Header.svelte';

	let scroll;
	let speed = 2;

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);

		// gsap.registerPlugin(CustomEase);

		// TweenMax.to(graph, 2.5, {
		// 	ease: CustomEase.create(
		// 		'overshoot',
		// 		'M0,0 C0,0 0.112,0.304 0.134,0.404 0.194,0.684 0.09,1.264 0.354,1.276 0.563,1.285 0.5,1.092 0.536,0.95 0.549,0.895 0.564,1.025 0.612,1.038 0.65,1.048 0.65,0.969 0.656,0.968 0.71,0.958 0.689,1.013 0.722,1.014 0.772,1.014 0.767,0.981 0.776,0.978 0.804,0.968 0.792,0.988 0.812,1 0.821,1.005 0.844,1.01 0.856,1.012 0.885,1.016 0.874,1.001 0.932,1 0.982,0.998 1,1 1,1 '
		// 	),
		// 	y: -500
		// });

		const slideUps = gsap.utils.toArray('.slide-up');
		for (let i = 0; i < slideUps.length; i++) {
			let slideUp = slideUps[i];

			gsap.from(slideUp, {
				scrollTrigger: {
					trigger: slideUp,
					start: '10px, 99%'
				},
				opacity: 0,
				y: 400,
				duration: 1,
				ease: 'Power3.easeOut'
			});
		}

		gsap.from('.slide-right', {
			scrollTrigger: {
				trigger: '.slide-right',
				start: '10px, 85%'
			},
			x: 400,
			opacity: 0,
			duration: 2,
			ease: 'Back.easeOut'
		});
		gsap.from('.slide-left', {
			scrollTrigger: {
				trigger: '.slide-left',
				start: '10px, 85%'
			},
			x: -400,
			opacity: 0,
			duration: 2,
			ease: 'Back.easeOut'
		});
	});
	ScrollTrigger.refresh();
</script>

<svelte:window bind:scrollY={scroll} />

<div class="pt-20" />
<Header />
<section
	class="bg-yellow-50 h-full z-10 bg-no-repeat bg-auto bg-center bg-fixed overflow-hidden"
	style="background-image: url('images/blue-splatter.png');
  background-size: 800px 500px;
"
>
	<div class="img-container py-10 mx-auto overflow-hidden h-[50vh] max-w-screen-xl">
		<img
			src="/images/paintbrushes.webp"
			class="rounded-full max-h-96 max-w-96 mx-auto shadow-black shadow-lg z-10"
			style:transform="translateY({scroll * (speed - 2.8)}px)"
			alt=""
		/>
	</div>
	<div class="mx-auto">
		<div class="sm:flex-row sm:mx-5 flex flex-col justify-between">
			<div
				class="parallax sm:w-1/2 bg-fixed bg-left bg-no-repeat object-cover max-w-screen-xl"
				style="background-image: url('images/bowl-of-paints.webp');
			height: 200px;
			max-width: 600px;
			min-width: 400px;

			<!-- min-width: 50%; -->
    "
			/>

			<div class="sm:w-1/2 px-2 h-full">
				<h2 class="slide-right text-right my-8 text-3xl">Lorem Ipsum</h2>
				<p class="slide-up">
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis ad nesciunt veniam
					modi corrupti nihil? Architecto quidem velit alias quod, similique magnam perferendis
					officiis eaque dolores ea laboriosam praesentium molestiae delectus ratione optio ut
					recusandae cum ipsa eum sunt. Quibusdam, quos! Fuga sit at veniam, perspiciatis, officiis
					eaque nihil quibusdam harum a possimus voluptates aspernatur enim fugit quaerat totam
					minima!
				</p>
			</div>
		</div>
		<div class="sm:flex-row sm:mx-5 flex flex-col justify-between h-full">
			<div class="sm:w-1/2 w-full px-2">
				<h2 class="slide-left my-8 text-3xl">Lorem Ipsum</h2>
				<p class="slide-up">
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis ad nesciunt veniam
					modi corrupti nihil? Architecto quidem velit alias quod, similique magnam perferendis
					officiis eaque dolores ea laboriosam praesentium molestiae delectus ratione optio ut
					recusandae cum ipsa eum sunt. Quibusdam, quos! Fuga sit at veniam, perspiciatis, officiis
					eaque nihil quibusdam harum a possimus voluptates aspernatur enim fugit quaerat totam
					minima!
				</p>
			</div>
			<div
				class="parallax sm:w-1/2 ml-auto object-cover bg-fixed bg-right bg-no-repeat"
				style="background-image: url('images/paints-and-brushes.webp');
			height: 200px;
			max-width: 600px;
			min-width: 400px;
    "
			/>
		</div>

		<!-- Bottom parallax section -->
		<div class="h-screen w-full text-center mt-24">
			<div
				class="parallax sm:w-1/2 mx-auto bg-fixed object-cover bg-center bg-no-repeat"
				style="background-image: url('images/spray-paint.webp');
			height: 100px;
			width: 80%;
    "
			/>
			<div
				class="parallax sm:w-1/2 my-24 mx-auto bg-fixed object-cover bg-center bg-no-repeat"
				style="background-image: url('images/brushes.webp');
			height: 100px;
			width: 100vw;

    "
			/>
			<div
				class="parallax bg-fixed mx-auto sm:w-1/2 object-cover bg-center bg-no-repeat"
				style="background-image: url('images/markers.webp');
			height: 100px;
			width: 90%;

    "
			/>
			<h2>ADD PARALLAX IMAGE</h2>
			<!-- <h1>ADD PARALLAX IMAGE</h1>
			<h2>ADD PARALLAX IMAGE</h2>
			<h1>ADD PARALLAX IMAGE</h1>
			<h2>ADD PARALLAX IMAGE</h2>
			<h1>ADD PARALLAX IMAGE</h1> -->
		</div>
	</div>
</section>
