<script>
	import '../app.css';
	import Navbar from '../components/Navbar.svelte';
	import Footer from '../components/Footer.svelte';
	// import { isOverlayOpen } from '../stores/OverlayStore.js';
	// import Overlay from '../components/Overlay.svelte';

	// import { onMount } from 'svelte';
	// import { gsap } from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger.js';

	ScrollTrigger.refresh();
</script>

<Navbar />

<div class="pt-20" />

<div>
	<slot><!-- optional fallback --></slot>
</div>

<Footer />
