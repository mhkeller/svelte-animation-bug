<script>
	import { fade } from 'svelte/transition';

	let items = $state([
		{id:1, title: 'I'},
		{id:2, title: 'Am'},
		{id:3, title: 'Yoda'}
	]);

	let i = $state(3);
	function addMore() {
		i = i + 1;
		items.push({ id: i, title: `Item ${i}` });
	}
</script>

<button onclick={addMore}>More</button>
<section>
	{#each items as item(item.id)}
		<div in:fade={{duration: 100, delay: 100}}>
			{item.title}
		</div>
	{/each}
</section>

<svelte:options runes />
<style>
	section {
		width: 100%;
		padding: 1em;
		display: flex;
		background: #ccc;
	}
	div {
		height: 1.5em;
		width: 10em;
		text-align: center;
		border: 1px solid black;
		margin: 0.2em;
		padding: 0.3em;
		flex: 1;
		background: #fc0
	}
</style>
