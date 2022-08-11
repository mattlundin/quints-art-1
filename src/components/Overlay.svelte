<script>
	import { fade } from 'svelte/transition';
	import { isOverlayOpen } from '../stores/OverlayStore.js';
</script>

<div
	class=" fixed bottom-0 left-0 flex justify-center items-center h-screen w-screen bg-gray-100 opacity-90 z-10"
	on:click={() => isOverlayOpen.set(false)}
	transition:fade
>
	<div
		class="relative p-10 h-11/12 w-11/12 bg-gray-900 text-white rounded-md opacity-90"
		on:click|stopPropagation
	>
		<button
			class="absolute top-2 right-3 text-4xl text-gray-300 hover:rotate-90 transition-transform duration-300"
			on:click={() => isOverlayOpen.set(false)}>&times;</button
		>
		<slot><!-- optional fallback --></slot>
	</div>
</div>
