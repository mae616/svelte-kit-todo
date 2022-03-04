<script lang="ts">
	import Item from '../components/item.svelte';
	export let todos: {
		content: string;
		id: string;
	}[];
	export let deleteTodo: (id: string) => void;
</script>

<h1>list</h1>
<ul>
	{#each todos as todo}
		<Item {todo} {deleteTodo} />
	{/each}
</ul>
