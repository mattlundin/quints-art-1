<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger.js';

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);

		gsap.from('.name', {
			opacity: 0,
			y: -300,
			x: -200,
			rotate: 180,
			duration: 1
		});

		const slideRights = gsap.utils.toArray('.slide-right');
		for (let i = 0; i < slideRights.length; i++) {
			let slideRight = slideRights[i];

			ScrollTrigger.matchMedia({
				// mobile
				'(max-width: 767px)': function () {
					gsap.from(
						slideRight,
						{
							scrollTrigger: {
								trigger: slideRight,
								start: '10px, 85%'
							},
							x: -400,
							opacity: 0,
							duration: 1.8,
							stagger: 1.1,
							ease: 'Back.easeOut'
						},
						'-=1.5'
					);
				},
				// desktop
				'(min-width: 768px)': function () {
					gsap.from(slideRight, {
						x: -400,
						opacity: 0,
						duration: 1.5,
						// stagger: 2,
						ease: 'Back.easeOut'
					});
				}
			});
		}

		//slc image
		ScrollTrigger.matchMedia({
			// mobile
			'(max-width: 767px)': function () {
				gsap.from('.grow-left', {
					scrollTrigger: {
						trigger: '.grow-left',
						start: '10px, 85%'
					},
					x: 400,
					opacity: 0,
					scale: 0.5,
					duration: 1.5,
					ease: 'Power3.easeOut'
				});
			},
			// desktop
			'(min-width: 768px)': function () {
				gsap.from('.grow-left', {
					x: 400,
					opacity: 0,
					scale: 0.5,
					duration: 1.5,
					ease: 'Power3.easeOut'
				});
			}
		});
		// inspirations header
		gsap.from('.fall-in', {
			scrollTrigger: {
				trigger: '.fall-in',
				start: '10px, 75%'
			},
			opacity: 0,
			scale: 5,
			duration: 2,
			ease: 'Power3.easeOut'
		});

		// bottom paragraph
		gsap.from('.slide-up', {
			scrollTrigger: {
				trigger: '.slide-up',
				start: '-350px 90%'
			},
			// opacity: 0,
			y: 500,
			scale: 0.1,
			duration: 1.5,
			ease: 'Power3.easeOut'
		});

		//records
		gsap.from('.records', {
			scrollTrigger: {
				trigger: '.records',
				start: '10px 85%'
			},
			opacity: 0,
			duration: 1.8,
			ease: 'none'
		});
	});

	ScrollTrigger.refresh();
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<!-- <div class="pt-20" /> -->
<div
	class="main bg-yellow-50 h-full z-10 bg-no-repeat bg-auto bg-center bg-fixed"
	style="background-image: url('images/blue-splatter.png');
  background-size: 800px 500px;
"
>
	<div class="header flex flex-col items-center pt-24 text-gray-200">
		<h2 class="name mt-3 xs:text-8xl md:text-9xl text-7xl text-shadow-lg shadow-black">Quints</h2>
	</div>

	<section class="sm:mt-48 mt-32 max-w-screen-xl sm:mx-auto h-full px-4">
		<div class="flex flex-col md:justify-between md:flex-row mt-8">
			<div class="md:w-1/2 md:mr-3 md:mb-0 mb-8 w-full">
				<h4 class="slide-right text-3xl font-bold">Background</h4>
				<p class="slide-right mb-6 mt-4">
					Lorem ipsum dolor sit, amet consectetur adipisicing elit. Culpa obcaecati provident
					veritatis perspiciatis velit nemo rem pariatur inventore. Exercitationem iure, officiis
					excepturi in quisquam eligendi.
				</p>
				<p class="slide-right ">
					Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ratione officiis adipisci
					cupiditate quo quod culpa nemo repellendus dolore ipsam eveniet, perferendis iusto, odio
					distinctio itaque, consectetur eos harum recusandae at illo cum? Autem libero odit illo.
					Voluptatem vel saepe necessitatibus, consequuntur reiciendis obcaecati dicta nihil!
				</p>
			</div>
			<div class="flex justify-center overflow-hidden">
				<img
					src="/images/slc-night.webp"
					alt=""
					class="grow-left align-center max-w-96 max-h-96 rounded-xl shadow-xl shadow-gray-600 opacity-95 overflow-hidden"
				/>
			</div>
		</div>
	</section>
	<section class="max-w-screen-xl sm:mx-auto h-full mt-12 px-4 overflow-hidden">
		<div class="flex items-center justify-center h-24 overflow-hidden">
			<h4 class="fall-in absolute text-4xl ml-auto font-bold overflow-hidden">Inspirations</h4>
		</div>
		<div class="max-w-screen-lg mx-auto mb-4">
			<p class="slide-up mb-12">
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui reiciendis optio laboriosam
				accusantium blanditiis vero delectus nesciunt molestias quas voluptatem soluta deleniti ipsa
				nostrum vel iure, officiis fuga, sed est odit debitis magnam! Magnam quibusdam dignissimos
				cum? Sapiente numquam nemo voluptatibus quis mollitia ut deserunt vitae hic repellendus?
				Dicta, ullam.
			</p>
		</div>
		<div class="flex justify-center mb-24">
			<img
				src="/images/records.webp"
				alt=""
				class="records md:w-3/5 w-full rounded-xl opacity-95"
			/>
		</div>
	</section>
</div>
