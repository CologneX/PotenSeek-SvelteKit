<script lang="ts">
	import { onMount } from 'svelte';
	import Logobox from '$lib/Logobox.svelte';

	// make the audio on 50%
	onMount(() => {
		const video = document.getElementById('player') as HTMLVideoElement;
		video.volume = 0.3;
	});

	import Carousel from 'svelte-carousel';
	import { browser } from '$app/environment';

	let carousel; // for calling methods of the carousel instance

	const handleNextClick = () => {
		carousel.goToNext();
	};
</script>

<svelte:head><title>PotenSeek - Home</title></svelte:head>

<div class="h-full flex justify-center place-items-center px-4 md:px-40" id="home">
	<div class="grid md:grid-cols-2 grid-cols-1 gap-4">
		<div class="grid content-center space-y-8">
			<h1 class="font-extrabold text-secondary-500">
				Segera Temukan Potensi Anak Anda dengan Bermain di Aplikasi Kami!
			</h1>
			<button
				class="btn btn-xl w-fit bg-tertiary-500 text-surface-500 text-2xl font-bold justify-self-center"
				>Pre-Register</button
			>
		</div>
		<video class="aspect-video h-96 justify-self-center" controls id="player">
			<track kind="captions" />
			<source src="/promosi.mp4" type="video/mp4" />
			Your browser does not support the video tag.
		</video>
	</div>
</div>
<div
	class="bg-cover md:bg-contain h-screen grid place-content-center bg-repeat-x"
	id="definition"
	style="background-image: url(BG.png)"
>
	<div class="px-4 md:px-40 grid justify-items-center">
		<h1 class="font-bold">
			Apa itu <span><img src="logo.png" alt="PotenSeek Logo" class="h-14 inline" /></span>?
		</h1>
		<div class="h-32 border-red-500">
			<Logobox />
		</div>

		<span class=" text-3xl font-medium text-center"
			>PotenSeek adalah sebuah aplikasi untuk orang tua yang mencari potensi anaknya dengan
			membiarkan anak-anaknya bersenang-senang menggunakan aplikasi PotenSeek.</span
		>
	</div>
</div>
<div class="h-fit w-screen px-4 md:px-40" id="how">
	<h1 class="font-bold flex justify-center">Cara Kerja PotenSeek</h1>
	{#if browser}
		<Carousel bind:this={carousel}>
			<div>
				<img src="mockup1.png" class="w-full" />
			</div>
			<div>
				<img src="mockup2.png" class="w-full" />
			</div>
		</Carousel>
	{/if}
</div>
<div
	class="h-fit grid justify-items-center space-y-10 pb-10 px-4 md:px-40 bg-cover md:bg-contain bg-repeat-x"
	style="background-image: url(BG.png)"
	id="contact"
>
	<span><img src="logo.png" alt="PotenSeek Logo" class="h-24" /></span>
	<h1 class="font-bold">Pre-Register</h1>
	<span class=" text-3xl font-medium text-center">
		Aplikasi ini sedang dalam tahap pengembangan, yuk bergabung dengan kami lebih awal dengan
		melakukan pre-register! Kamu bisa berkesempatan menjadi tester produk kami yang pertama! Segera
		daftar sekarang!
	</span>

	<div class="border-2 border-gray-500 card p-10">
		<form action="POST" class="grid gap-y-4">
			<label class="label">
				<span class="font-bold text-lg">Nama Lengkap</span>
				<input type="text" class="input variant-form-material" />
			</label>
			<label class="label">
				<span class="font-bold text-lg">Email</span>
				<input type="email" class="input variant-form-material" />
			</label>
			<button
				class="btn btn-lg bg-primary-500 text-surface-500 text-2xl font-bold justify-self-center"
			>
				Pre-Register
			</button>
		</form>
	</div>
</div>
