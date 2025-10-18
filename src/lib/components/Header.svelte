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

	function closeMenu() {
		menuOpen = false;
	}
</script>

<header
	class="fixed z-50 w-full border-b border-gray-200 bg-white/80 backdrop-blur-lg transition-all duration-300"
>
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-16 items-center justify-between">
			<!-- Logo -->
			<a
				href="/"
				class="bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-2xl font-bold text-transparent transition-all duration-300 hover:from-blue-700 hover:to-purple-700"
			>
				MyBrand
			</a>

			<!-- Desktop Navigation -->
			<div class="hidden items-center gap-8 md:flex">
				<nav>
					<ul class="flex items-center gap-1">
						<li>
							<a
								href="/"
								class="rounded-lg px-4 py-2 font-medium text-gray-700 transition-all duration-200 hover:bg-blue-50 hover:text-blue-600"
							>
								Home
							</a>
						</li>
						<li>
							<a
								href="/about"
								class="rounded-lg px-4 py-2 font-medium text-gray-700 transition-all duration-200 hover:bg-blue-50 hover:text-blue-600"
							>
								About
							</a>
						</li>
						<li>
							<a
								href="/contact"
								class="rounded-lg px-4 py-2 font-medium text-gray-700 transition-all duration-200 hover:bg-blue-50 hover:text-blue-600"
							>
								Contact
							</a>
						</li>
					</ul>
				</nav>

				<!-- Theme Toggle -->
				<button
					on:click={toggleTheme}
					class="group relative rounded-xl bg-gradient-to-br from-gray-100 to-gray-200 p-2.5 shadow-sm transition-all duration-300 hover:from-gray-200 hover:to-gray-300 hover:shadow-md"
					aria-label="Toggle theme"
				>
					<div class="relative h-5 w-5">
						<div
							class="absolute inset-0 transition-all duration-300"
							class:opacity-0={darkMode}
							class:rotate-180={darkMode}
							class:scale-0={darkMode}
						>
							<Sun size="20" class="text-amber-500 group-hover:text-amber-600" />
						</div>
						<div
							class="absolute inset-0 transition-all duration-300"
							class:opacity-0={!darkMode}
							class:rotate-180={!darkMode}
							class:scale-0={!darkMode}
						>
							<Moon size="20" class="text-indigo-600 group-hover:text-indigo-700" />
						</div>
					</div>
				</button>
			</div>

			<!-- Mobile Controls -->
			<div class="flex items-center gap-3 md:hidden">
				<button
					on:click={toggleTheme}
					class="group relative rounded-xl bg-gradient-to-br from-gray-100 to-gray-200 p-2.5 shadow-sm transition-all duration-300 hover:from-gray-200 hover:to-gray-300 hover:shadow-md"
					aria-label="Toggle theme"
				>
					<div class="relative h-5 w-5">
						<div
							class="absolute inset-0 transition-all duration-300"
							class:opacity-0={darkMode}
							class:rotate-180={darkMode}
							class:scale-0={darkMode}
						>
							<Sun size="20" class="text-amber-500" />
						</div>
						<div
							class="absolute inset-0 transition-all duration-300"
							class:opacity-0={!darkMode}
							class:rotate-180={!darkMode}
							class:scale-0={!darkMode}
						>
							<Moon size="20" class="text-indigo-600" />
						</div>
					</div>
				</button>

				<button
					on:click={toggleMenu}
					class="rounded-xl bg-gradient-to-br from-gray-100 to-gray-200 p-2.5 shadow-sm transition-all duration-300 hover:from-gray-200 hover:to-gray-300 hover:shadow-md"
					aria-label="Toggle menu"
				>
					<div class="relative h-5 w-5">
						<div
							class="absolute inset-0 transition-all duration-300"
							class:opacity-0={menuOpen}
							class:rotate-90={menuOpen}
							class:scale-0={menuOpen}
						>
							<Menu size="20" class="text-gray-700" />
						</div>
						<div
							class="absolute inset-0 transition-all duration-300"
							class:opacity-0={!menuOpen}
							class:-rotate-90={!menuOpen}
							class:scale-0={!menuOpen}
						>
							<X size="20" class="text-gray-700" />
						</div>
					</div>
				</button>
			</div>
		</div>
	</div>

	<!-- Mobile Menu -->
	<div
		class="overflow-hidden border-t border-gray-200 transition-all duration-300 ease-in-out md:hidden"
		style="max-height: {menuOpen ? '300px' : '0'}; opacity: {menuOpen ? '1' : '0'}"
	>
		<nav class="bg-gradient-to-b from-white to-gray-50">
			<ul class="space-y-1 px-4 py-4">
				<li class="transform transition-all duration-300" style="transition-delay: 50ms">
					<a
						href="/"
						on:click={closeMenu}
						class="block rounded-lg px-4 py-3 font-medium text-gray-700 transition-all duration-200 hover:bg-blue-50 hover:text-blue-600"
					>
						Home
					</a>
				</li>
				<li class="transform transition-all duration-300" style="transition-delay: 100ms">
					<a
						href="/about"
						on:click={closeMenu}
						class="block rounded-lg px-4 py-3 font-medium text-gray-700 transition-all duration-200 hover:bg-blue-50 hover:text-blue-600"
					>
						About
					</a>
				</li>
				<li class="transform transition-all duration-300" style="transition-delay: 150ms">
					<a
						href="/contact"
						on:click={closeMenu}
						class="block rounded-lg px-4 py-3 font-medium text-gray-700 transition-all duration-200 hover:bg-blue-50 hover:text-blue-600"
					>
						Contact
					</a>
				</li>
			</ul>
		</nav>
	</div>
</header>
