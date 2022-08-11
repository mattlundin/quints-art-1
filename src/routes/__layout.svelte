<script>
	import '../app.css';
	import Navbar from '../components/Navbar.svelte';
	import Footer from '../components/Footer.svelte';
	// import { isOverlayOpen } from '../stores/OverlayStore.js';
	// import Overlay from '../components/Overlay.svelte';
</script>

<Navbar />

<div class="pt-20" />

<div>
	<slot><!-- optional fallback --></slot>
</div>

<Footer />
