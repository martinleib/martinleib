<script>
	import Header from './Header.svelte';
	import SaleBanner from './SaleBanner.svelte';
	import Footer from './Footer.svelte'
	import '../app.sass';
	import '../../node_modules/bootstrap/dist/css/bootstrap.min.css';
</script>

<svelte:head>
	<title>Martin Leib</title>
	<meta name="description" content="Martin Leib kit store" />
</svelte:head>


<Header />
<SaleBanner />

<main>
	<slot />
</main>

<footer>
	<Footer />
</footer>