<script>
	import '../app.css';
	import Navbar from '$lib/components/Navbar.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
	<title>Nama Perusahaan</title>
</svelte:head>

<Navbar />
<slot />
<Footer />
