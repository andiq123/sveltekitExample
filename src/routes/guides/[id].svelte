<script context="module">
	export async function load({ fetch, params }) {
		const { id } = params;
		const link = 'https://jsonplaceholder.typicode.com/todos/' + id;

		const res = await fetch(link);
		const guide = await res.json();

		if (res.ok) {
			return {
				props: {
					guide
				}
			};
		}

		return {
			status: 301,
			redirect: '/guides'
		};
	}
</script>

<script>
	export let guide;
</script>

<div class="guide">
	<div class="guide" class:completed={guide.completed} href={guide.id}>
		<p><b>Title:</b> {guide.title}</p>
		<p><b>Status:</b> {guide.completed ? 'Completed' : 'Pending'}</p>
	</div>
</div>

<style>
	.guide {
		border: 1px solid #ccc;
		margin: 0 0 10px 0;
		background-color: white;
		padding: 20px;
		display: flex;
		flex-flow: column wrap;
		gap: 20px;
		justify-content: center;
	}
</style>
