<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>
	


<style>
	main {
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 1em 2em;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>
<head>
<meta name='theme-color' content='#ff3e00'>
<link rel='icon' type='image/png' href='favicon.png'>
</head>

<Nav {segment}/>

<main>
	<slot></slot>
</main>