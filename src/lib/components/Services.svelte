<script>
	import { services } from '$lib/data/services';
</script>

<section class="bg-gray-50 py-20 text-center">
	<h2 class="mb-10 text-3xl font-bold">Servansi Kami</h2>
	<div class="grid gap-6 px-8 md:grid-cols-3">
		{#each services as s}
			<div class="rounded-xl bg-white p-6 shadow-md hover:shadow-lg">
				<h3 class="mb-2 text-xl font-semibold">{s.title}</h3>
				<p class="text-gray-600">{s.desc}</p>
			</div>
		{/each}
	</div>
</section>
