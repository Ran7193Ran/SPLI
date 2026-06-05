<script>
	import Header from '../../components/Header.svelte';
	import Footer from '../../components/Footer.svelte';

	let y = $state(0);
	let innerHeight = $state(0);
	let innerWidth = $state(0);
</script>

<svelte:window
	bind:scrollY={y}
	bind:innerHeight={innerHeight}
	bind:innerWidth={innerWidth}
/>

<Header {y}  />
<Footer />