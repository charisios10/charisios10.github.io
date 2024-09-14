<script>
	export const prerender = true;
	import { onMount } from 'svelte';
	import Navigation from '$lib/components/Navigation.svelte';
	let stars = [];

	onMount(() => {
		for (let i = 0; i < 100; i++) {
			stars.push({
				x: Math.random() * 100,
				y: Math.random() * 100,
				size: Math.random() * 2 + 1
			});
		}
	});
</script>

<Navigation />

<main>
	<slot />
</main>

<div class="stars">
	{#each stars as star}
		<div
			class="star"
			style="left: {star.x}%; top: {star.y}%; width: {star.size}px; height: {star.size}px;"
		></div>
	{/each}
</div>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: Arial, sans-serif;
		background-color: #0a0a2a;
		color: #ffffff;
	}

	main {
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem;
	}

	.stars {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: -1;
	}

	.star {
		position: absolute;
		background-color: #ffffff;
		border-radius: 50%;
		animation: twinkle 5s infinite;
	}

	@keyframes twinkle {
		0%,
		100% {
			opacity: 1;
		}
		50% {
			opacity: 0.5;
		}
	}
</style>
