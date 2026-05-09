<script>
	import favicon from '$lib/assets/favicon.svg';
	import "../app.css"
  	import Header from '../components/Header.svelte';
    import Main from '../components/Main.svelte';

	let { children } = $props();

	let y = $state();
	let innerHeight = $state(0);
	let innerWidth = $state(0);

	function goTop() {
		document.body.scrollIntoView();
	}
</script>
<Header y={y} {innerHeight}/>
<Main/>

