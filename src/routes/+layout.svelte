<script lang="ts">
	import '../theme.postcss';
	import '@skeletonlabs/skeleton/styles/all.css';
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
	import Logo from '$lib/Logo.svelte';
	import Email from '$lib/Email.svelte';
	import Instagram from '$lib/Instagram.svelte';
	// This is a helper function to scroll to a specific element on the page
	export function scrollIntoView(id: string) {
		const element = document.getElementById(id);
		if (element) {
			element.scrollIntoView({ behavior: 'smooth' });
		}
	}
</script>

<!-- App Shell -->
<AppShell slotHeader="font-bold">
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar
			slotDefault="place-self-center grid space-x-4"
			gridColumns="grid-cols-1"
			shadow="drop-shadow-lg"
		>
			<div class="btn-group [&>*+*]:border-transparent">
				<button on:click={() => scrollIntoView('home')}
					><span class="text-primary-500">Home</span></button
				>
				<button on:click={() => scrollIntoView('definition')}>Apa itu PotenSeek</button>
				<a href="/"><img src="logo.png" alt="Potenseek Logo" class="h-12" /></a>
				<button on:click={() => scrollIntoView('how')}>Cara Kerja</button>
				<button on:click={() => scrollIntoView('contact')}>Hubungi Kami</button>
			</div>
		</AppBar>
	</svelte:fragment>
	<main class="h-full w-full bg-primary-500 grid grid-rows-2 justify-items-center">
		<slot />
	</main>
	<svelte:fragment slot="pageFooter">
		<footer class="bg-[#0D2834] grid grid-flow-row justify-items-center py-8 text-white">
			<img src="logo.png" alt="PotenSeek Logo" class="h-12" /><br />
			<div class="btn-group [&>*+*]:border-transparent grid grid-cols-1 md:grid-cols-2">
				<button class="btn"><span><Email /></span><span>potenseek_id</span></button>
				<button class="btn"><span><Instagram /></span><span>potenseekid@gmail.com</span></button>
			</div>
			<p>&copy 2023 PotenSeek, Surabaya, Indonesia</p>
		</footer>
	</svelte:fragment>
</AppShell>
