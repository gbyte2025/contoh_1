<script>
	import { onMount } from 'svelte';
	let scrolled = false;
	let menuOpen = false;
	const toggleMenu = () => {
		menuOpen = !menuOpen;
	};

	onMount(() => {
		const handleScroll = () => {
			scrolled = window.scrollY > 50;
		};
		window.addEventListener('scroll', handleScroll);
		return () => window.removeEventListener('scroll', handleScroll);
	});
</script>

<header
	class={`fixed top-0 left-0 z-50 w-full transition-all duration-500 ${
		scrolled ? 'bg-white shadow-md' : 'bg-transparent'
	}`}
>
	<div class="mx-auto flex max-w-7xl items-center justify-between px-6 py-4 text-sm font-semibold">
		<!-- Left Navigation -->
		<nav class="hidden space-x-10 text-gray-800 uppercase md:flex">
			<a href="#berries" class="transition hover:text-green-600">Berries</a>
			<a href="#who-we-are" class="transition hover:text-green-600">Who We Are</a>
		</nav>

		<!-- Logo Center -->
		<a href="/" class="flex items-center justify-center">
			<img
				src="/logo.png"
				alt="Always Fresh"
				class="h-10 w-auto transition-transform duration-500 hover:scale-105"
			/>
		</a>

		<!-- Right Navigation -->
		<nav class="hidden space-x-10 text-gray-800 uppercase md:flex">
			<a href="#how-we-grow" class="transition hover:text-green-600">How We Grow</a>
			<a href="#recipes" class="transition hover:text-green-600">Recipes</a>
		</nav>

		<!-- Mobile Menu Button -->
		<button
			class="text-gray-800 md:hidden"
			on:click={() => (menuOpen = !menuOpen)}
			aria-label="Toggle menu"
		>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
				class="h-7 w-7"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16M4 18h16"
				/>
			</svg>
		</button>

		<!-- Mobile Menu -->
		{#if menuOpen}
			<div class="bg-white shadow-md md:hidden">
				<nav class="flex flex-col space-y-3 p-4">
					<a href="#about" class="transition-colors hover:text-blue-600">Tentang Kami</a>
					<a href="#services" class="transition-colors hover:text-blue-600">Layanan</a>
					<a href="#portfolio" class="transition-colors hover:text-blue-600">Portofolio</a>
					<a href="#contact" class="transition-colors hover:text-blue-600">Kontak</a>
					<hr />
					<a
						href="/login"
						class="block rounded-lg bg-blue-600 py-2 text-center text-white hover:bg-blue-700"
					>
						Masuk
					</a>
				</nav>
			</div>
		{/if}
	</div>
</header>

<style>
	header {
		backdrop-filter: blur(10px);
	}
</style>
