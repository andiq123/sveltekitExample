<script context="module">
	export async function load({ fetch }) {
		const link = 'https://jsonplaceholder.typicode.com/todos/';

		const res = await fetch(link);
		const guides = await res.json();

		if (res.ok) {
			return {
				props: {
					guides
				}
			};
		}

		return {
			status: res.status,
			error: new Error('Could not fetch epta')
		};
	}
</script>

<script>
	export let guides = [];
</script>

<div class="guides">
	{#each guides as guide (guide.id)}
		<a
			sveltekit:prefetch
			class="guide"
			class:completed={guide.completed}
			href={'/guides/' + guide.id}
		>
			<p><b>Title:</b> {guide.title}</p>
			<p><b>Status:</b> {guide.completed ? 'Completed' : 'Pending'}</p>
		</a>
	{/each}
</div>

<style>
	.guides {
		display: flex;
		flex-flow: row wrap;
		gap: 20px;
		width: 80%;
		margin: 0 auto;
	}
	.guide {
		text-decoration: none;
		color: black;
		border: 1px solid #ccc;
		margin: 0 0 10px 0;
		background-color: white;
		padding: 20px;
		cursor: pointer;
		display: flex;
		flex-flow: column wrap;
		gap: 20px;
		justify-content: center;
	}
	.completed {
		background-color: rgb(190, 228, 188);
	}
</style>
