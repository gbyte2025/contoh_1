<script>
	import { Sun, Moon, Menu, X } from 'lucide-svelte';

	let darkMode = false;
	let menuOpen = false;

	function toggleTheme() {
		darkMode = !darkMode;
	}

	function toggleMenu() {
		menuOpen = !menuOpen;
	}
</script>

<header class="fixed z-50 w-full bg-white">
	<div class="m-2 flex flex-row items-center justify-between">
		<a href="/" class="p-2 text-2xl font-bold text-blue-600">MyBrand</a>

		<!-- DESKTOP -->
		<div class="hidden flex-row items-center gap-4 md:flex">
			<nav>
				<ul class="flex flex-row gap-5">
					<li><a href="/" class="hover:text-blue-600">Home</a></li>
					<li><a href="/about" class="hover:text-blue-600">About</a></li>
					<li><a href="/contact" class="hover:text-blue-600">Contact</a></li>
				</ul>
			</nav>

			<div class="h-6 w-px bg-black"></div>

			<button
				on:click={toggleTheme}
				class="cursor-pointer rounded-md bg-gray-100 p-2 shadow-md transition hover:bg-gray-200"
			>
				{#if darkMode}
					<Moon size="22" />
				{:else}
					<Sun size="22" />
				{/if}
			</button>
		</div>

		<!-- MOBILE -->
		<div class="flex flex-row items-center gap-3 md:hidden">
			<button
				on:click={toggleMenu}
				class="cursor-pointer rounded-md bg-gray-100 p-2 shadow-md transition hover:bg-gray-200"
			>
				{#if menuOpen}
					<X size="22" />
				{:else}
					<Menu size="22" />
				{/if}
			</button>

			<button
				on:click={toggleTheme}
				class="cursor-pointer rounded-md bg-gray-100 p-2 shadow-md transition hover:bg-gray-200"
			>
				{#if darkMode}
					<Moon size="22" />
				{:else}
					<Sun size="22" />
				{/if}
			</button>
		</div>
	</div>

	<!-- MENU MOBILE -->
	{#if menuOpen}
		<div class="absolute w-full bg-white shadow-md md:hidden">
			<nav>
				<ul class="flex flex-col items-center gap-3 border-t border-gray-200 py-4">
					<li>
						<a href="/" class="block text-center">Home</a>
					</li>
					<li>
						<a href="/about" class="block text-center">About</a>
					</li>
					<li>
						<a href="/contact" class="block text-center">Contact</a>
					</li>
				</ul>
			</nav>
		</div>
	{/if}
</header>
