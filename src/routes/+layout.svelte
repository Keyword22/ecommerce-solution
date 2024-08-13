<script>
	import '../app.css';
	import Header from '$lib/components/Header.svelte';
	import Menu from '$lib/components/Menu.svelte';
	import { slide } from 'svelte/transition';
	import { quadIn } from 'svelte/easing';

	let menuOpen = true;
</script>

<main class="flex relative">
	{#if menuOpen}
		<div transition:slide={{ delay: 250, duration: 300, easing: quadIn, axis: 'x' }}>
			<Menu on:closeMenu={() => (menuOpen = false)} />
		</div>
	{:else}
		<div class="bg-gray-900 h-screen">
			<button
                class="flex mt-5"
				transition:slide={{ delay: 250, duration: 300, easing: quadIn, axis: 'x' }}
				on:click={() => (menuOpen = true)}
				><img class="w-6 h-6" src="https://www.svgrepo.com/show/124304/three-dots.svg" /></button
			>
		</div>
	{/if}

	<div class="relative w-full m-0">
		<Header />
		<div>
			<slot />
		</div>
	</div>
</main>

<style lang="postcss">
	main {
		font-family: Marxiana Trial Antiqua;
	}
</style>
