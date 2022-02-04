<script lang="ts">
	export let title = 'ninja gaming';
	const titleCase = (e: string) => {
		return e
			.split(' ')
			.map((x) => x.slice(0, 1).toUpperCase() + x.slice(1))
			.join(' ');
	};
</script>

<nav>
	<h2>{titleCase(title)}</h2>
	<ul>
		<li>
			<a href="/" sveltekit:prefetch>Home</a>
			<a href="/about" sveltekit:prefetch>About Page</a>
			<a href="/guides" sveltekit:prefetch>Guides</a>
		</li>
	</ul>
</nav>

<style>
	nav {
		padding: 0;
		margin: 0;
		display: grid;
		grid-template-columns: 0.3fr 1fr;
		background-color: rgb(248, 244, 220);
	}
</style>
