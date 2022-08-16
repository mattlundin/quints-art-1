<script>
	import { onMount } from 'svelte';
	// import { gsap } from 'gsap';
	// import { ScrollTrigger } from 'gsap/dist/ScrollTrigger.js';
	import { gsap, ScrollTrigger } from '../gsap';

	import Header from '../components/Header.svelte';

	let scroll;
	let speed = 2;

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);

		const slideUps = gsap.utils.toArray('.slide-up');
		for (let i = 0; i < slideUps.length; i++) {
			let slideUp = slideUps[i];

			gsap.from(slideUp, {
				scrollTrigger: {
					trigger: slideUp,
					start: '-200px 99%'
				},
				opacity: 0,
				y: 400,
				duration: 1.2,
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

<svelte:head>
	<title>Home</title>
</svelte:head>

<svelte:window bind:scrollY={scroll} />

<Header />
<div
	class="bg-yellow-50 h-full z-10 bg-no-repeat bg-auto bg-center bg-fixed overflow-hidden"
	style="background-image: url('images/blue-splatter.png');
  background-size: 800px 500px;
"
>
	<div class="img-container pt-10 mx-auto overflow-hidden h-[50vh] opacity-95">
		<img
			src="/images/paintbrushes.webp"
			class="rounded-full max-w-96 mx-auto shadow-black shadow-lg z-10"
			style:transform="translateY({scroll * (speed - 2.8)}px)"
			alt=""
		/>
	</div>
	<section class="sm:-my-24 sm:pb-0 -my-48 pb-56 mx-auto">
		<div class="sm:flex-row sm:mx-5 flex flex-col justify-between">
			<div
				class="parallax sm:w-1/2 w-full mb-8 bg-fixed sm:bg-left bg-center bg-no-repeat object-cover max-w-screen-xl"
				style="background-image: url('images/bowl-of-paints.webp');
			height: 250px;
			max-width: 600px;
			min-width: 300px;

			<!-- min-width: 50%; -->
    "
			/>

			<div class="trigger sm:w-1/2 px-2 h-full">
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
		<div class="sm:flex-row sm:mx-5 flex flex-col-reverse justify-between h-full">
			<div class="trigger sm:w-1/2 w-full px-2">
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
				class="parallax sm:w-1/2 w-full my-8 ml-auto object-cover bg-fixed sm:bg-right bg-center bg-no-repeat"
				style="background-image: url('images/paints-and-brushes.webp');
			height: 250px;
			max-width: 600px;
			min-width: 300px;
    "
			/>
		</div>

		<!-- Bottom parallax section -->
		<div class="sm:mb-72 pb-48 h-full w-screen mt-24">
			<div
				class="parallax w-full mx-auto bg-fixed object-cover bg-center bg-no-repeat"
				style="background-image: url('images/brushes.webp');
			height: 80px;
    "
			/>
			<div
				class="parallax mx-auto my-16 bg-fixed object-cover bg-center bg-no-repeat"
				style="background-image: url('images/colored-pencils.webp');
			height: 80px;
    "
			/>
			<div
				class="parallax bg-fixed mx-auto object-cover bg-center bg-no-repeat"
				style="background-image: url('images/markers.webp');
			height: 80px;
    "
			/>
			<div
				class="parallax mx-auto my-16 bg-fixed object-cover bg-center bg-no-repeat"
				style="background-image: url('images/spray-paint.webp');
			height: 80px;
    "
			/>
			<div
				class="parallax mx-auto bg-fixed object-cover bg-center bg-no-repeat"
				style="background-image: url('images/chalk.webp');
			height: 80px;
    "
			/>
		</div>
		<!-- <div class="h-screen" /> -->
	</section>
</div>
