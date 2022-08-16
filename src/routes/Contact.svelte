<script>
	import { onMount } from 'svelte';
	import { gsap, ScrollTrigger } from '../gsap';

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);

		gsap.from('.gallery-header', {
			y: 300,
			opacity: 0,
			duration: 1
		});

		let tl = gsap.timeline({
			scrollTrigger: {
				trigger: '.gallery-header',
				start: 'bottom 80%'
			}
		});

		tl.from;
	});

	ScrollTrigger.refresh();
</script>

<svelte:head>
	<title>Contact</title>
</svelte:head>

<div
	class="main bg-yellow-50 h-full pb-24 px-2 z-10 bg-no-repeat bg-auto bg-center bg-fixed"
	style="background-image: url('images/blue-splatter.png');
  background-size: 800px 500px;
"
>
	<div class="header flex flex-col items-center mb-48 pt-24 text-gray-200">
		<h2
			class="gallery-header mt-3 xs:text-7xl sm:text-8xl md:text-9xl text-6xl text-shadow-lg shadow-black"
		>
			Contact
		</h2>
	</div>

	<!-- Contact Form -->
	<div
		class="w-full md:w-2/4 md:max-w-full mx-auto bg-slate-800 rounded-lg shadow-2xl opacity-95 shadow-black"
	>
		<div class="p-6 border border-gray-300 sm:rounded-md outline-none border-none">
			<form action="https://api.staticforms.xyz/submit" method="post" class="">
				<!-- replace with StaticForms accessKey -->
				<input type="hidden" name="accessKey" value="replace-with-access-key" />
				<!-- replace with URL to redirect to -->
				<input type="hidden" name="redirectTo" value="urlNameHere" />
				<label class="block mb-6">
					<span class="text-gray-200">Name</span>
					<input
						type="text"
						name="name"
						class="
							block
							w-full
							px-2
							py-2
							border-gray-300
							rounded-md
							shadow-sm
							focus:border-indigo-300
							focus:ring
							focus:ring-indigo-200
							focus:ring-opacity-50
						"
						placeholder="Enter Your Name"
					/>
				</label>
				<label class="block mb-6">
					<span class="text-gray-200">Email address</span>
					<input
						name="email"
						type="email"
						class="
							block
							w-full
							px-2
							py-2
							border-gray-300
							rounded-md
							shadow-sm
							focus:border-indigo-300
							focus:ring
							focus:ring-indigo-200
							focus:ring-opacity-50
						"
						placeholder="Enter Your Email"
						required
					/>
				</label>
				<label class="block mb-6">
					<span class="text-gray-200">Message</span>
					<textarea
						name="message"
						class="
							block
							w-full
							px-2
							py-2
							border-gray-300
							rounded-md
							shadow-sm
							focus:border-indigo-300
							focus:ring
							focus:ring-indigo-200
							focus:ring-opacity-50
						"
						rows="3"
						placeholder="Enter Your Message"
					/>
				</label>
				<div class="mb-6">
					<button
						type="submit"
						class="
							h-10
							px-5
							text-gray-200
							bg-sky-500
							font-bold
							rounded-lg
							transition 
							ease-in-out
							duration-200
							focus:shadow-outline
							hover:scale-110
							hover:bg-sky-700
						"
					>
						Contact Me
					</button>
				</div>
			</form>
		</div>
	</div>
	<!-- <div class="flex items-center flex-col pt-24 pb-12">
		<p class="text-2xl">Or find me on Social Media</p>
		<div class="socials flex mt-12">
			<div class="rounded-full px-2">
				<a href="#"><i class="fa-brands fa-facebook text-4xl" /></a>
			</div>
			<div class="rounded-full px-2">
				<a href="#"><i class="fa-brands fa-twitter text-4xl" /></a>
			</div>
			<div class="rounded-full px-2">
				<a href="#"><i class="fa-brands fa-instagram text-4xl" /></a>
			</div>
		</div>
	</div> -->
	<div class="h-screen-1/2" />
</div>
