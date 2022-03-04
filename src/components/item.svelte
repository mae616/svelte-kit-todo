<script lang="ts">
	export let todo: { content: string; id: string };
	export let deleteTodo: (id: string) => void;
	let check: boolean;
</script>

<li class={check ? 'checked' : 'unchecked'}>
	<input type="checkbox" bind:checked={check} />
	{todo.content}
	<button
		on:click={() => {
			deleteTodo(todo.id);
		}}>削除</button
	>
</li>

<style>
	.checked {
		text-decoration: line-through;
	}
</style>
