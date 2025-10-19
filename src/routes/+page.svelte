<script>
	import Header from '$lib/components/Header.svelte';
</script>

<Header />

<!-- <img src="/images/background.png" alt="Logo Perusahaan" style="width: 100%;" /> -->
<section class="relative flex flex-col items-center bg-white py-10">
	<!-- Foto profil -->
	<div class="relative">
		<img src="/images/background.png" alt="Profile" class="border-white shadow-lg md:" />
		<!-- Bagian bawah (stats) -->
		<div class="absolute bottom-0 left-1/2 flex translate-x-[-50%] translate-y-[50%] gap-4">
			<div class="rounded-lg bg-cyan-500 px-6 py-4 text-center text-white shadow">
				<h3 class="text-2xl font-bold">10++</h3>
				<p class="text-sm">projects</p>
			</div>
			<div class="rounded-lg bg-amber-400 px-6 py-4 text-center text-white shadow">
				<h3 class="text-2xl font-bold">6</h3>
				<p class="text-sm">active</p>
			</div>
			<div class="rounded-lg bg-lime-500 px-6 py-4 text-center text-white shadow">
				<h3 class="text-2xl font-bold">1</h3>
				<p class="text-sm">pay projects</p>
			</div>
		</div>
	</div>
</section>

<section class="h-screen"></section>

<section class="h-screen"></section>
