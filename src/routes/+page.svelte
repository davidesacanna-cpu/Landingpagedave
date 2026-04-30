<script>
	import { onMount } from 'svelte';
	import Desktop from '../lib/components/Desktop.svelte';
	import Tablet from '../lib/components/Tablet.svelte';
	import Mobile from '../lib/components/Mobile.svelte';

	let screenWidth = 1512;
	let currentView = 'desktop';

	onMount(() => {
		const handleResize = () => {
			screenWidth = window.innerWidth;
			// Desktop: > 1024px, Tablet: 768-1024px, Mobile: < 768px
			if (screenWidth < 768) {
				currentView = 'mobile';
			} else if (screenWidth < 1024) {
				currentView = 'tablet';
			} else {
				currentView = 'desktop';
			}
		};

		handleResize();
		window.addEventListener('resize', handleResize);

		return () => window.removeEventListener('resize', handleResize);
	});
</script>

<svelte:window bind:innerWidth={screenWidth} />

<main class="landing-page">
	{#if currentView === 'mobile'}
		<Mobile />
	{:else if currentView === 'tablet'}
		<Tablet />
	{:else}
		<Desktop />
	{/if}
</main>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		background-color: #0a0a0a;
		color: #fafafa;
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue',
			Arial, sans-serif;
		overflow-x: hidden;
	}

	:global(html) {
		scroll-behavior: smooth;
	}

	:global(*) {
		box-sizing: border-box;
	}

	main {
		width: 100%;
		background-color: #0a0a0a;
	}
</style>
