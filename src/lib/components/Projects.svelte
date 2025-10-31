<script>
	import { projects } from '$lib/data/projects';
</script>

<section class="bg-white py-20 text-center">
	<h2 class="mb-10 text-3xl font-bold">Projek Unggulan</h2>
	<div class="grid gap-6 px-8 md:grid-cols-3">
		{#each projects as p}
			<div class="overflow-hidden rounded-lg shadow-md">
				<img src={p.image} alt={p.title} class="h-48 w-full object-cover" />
				<div class="p-4 text-left">
					<h3 class="mb-2 text-lg font-semibold">{p.title}</h3>
					<p class="text-sm text-gray-600">{p.desc}</p>
				</div>
			</div>
		{/each}
	</div>
</section>
