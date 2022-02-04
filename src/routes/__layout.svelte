<script lang="ts">
	import '../style/global.css';
	import Nav from '$lib/nav.svelte';
</script>

<header>
	<Nav />
</header>
<main>
	<slot />
</main>
<footer>Andi Copyright 2022</footer>

<style>
	main {
		background-color: rgb(233, 217, 217);
		height: fit-content;
	}

	footer {
		padding: 20px;
		height: 100%;
		text-align: center;
		background-color: rgb(220, 224, 228);
	}
</style>
