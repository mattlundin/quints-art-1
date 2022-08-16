<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';

	let scroll;
	let speed = 2;

	onMount(() => {
		gsap.from('.header', {
			opacity: 0,
			scale: 0.1,
			rotate: -360,
			duration: 1,
			ease: 'Bounce.easeOut, y: -500'
		});
		gsap.to('.header', {
			rotationX: '-=360',
			duration: 1
		});
	});
</script>

<svelte:window bind:scrollY={scroll} />

<header
	class="sm:h-[50vh] h-[calc(50vh-80px)] relative overflow-hidden bg-no-repeat bg-cover pt-40  -z-10"
	style="background-image: url('/images/oil-paints.webp');
	background-position: 50%;
	background-repeat: no-repeat;
	"
>
	<div
		class="absolute top-0 left-0 flex justify-center w-full h-full overflow-hidden bg-fixed"
		style="background-color: rgba(0,0,0,0.35)"
	>
		<h3
			class="header xs:text-6xl sm:text-8xl lg:text-9xl text-5xl text-center pb-20 my-auto text-gray-300 text-shadow-lg shadow-sky-500"
			style:transform="translateY({scroll * speed}px)"
		>
			Quints Art
		</h3>
	</div>
</header>
