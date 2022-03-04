<script lang="ts">
	import { count } from '../store.js';
	import Form from '../components/form.svelte';
	import List from '../components/list.svelte';
	import { nanoid } from 'nanoid';
	import { goto } from '$app/navigation';

	// npm run dev -- --open
	let todos = [{ content: '掃除', id: 'test' }];
	const addTodo = (value: string) => {
		todos = [...todos, { content: value, id: nanoid() }];
	};
	const deleteTodo = (id: string) => {
		todos = todos.filter((todo) => todo.id !== id);
	};

	let countValue: number;

	count.subscribe((value) => {
		countValue = value;
	});

	// {@debug todos}
</script>

<h1>TODO APP</h1>
<Form {addTodo} />
<List {todos} {deleteTodo} />
<p>{countValue}</p>
<button
	on:click={() => {
		goto('/test');
	}}>goto</button
>

<a href="/test">test</a>

<style>
	h1 {
		color: red;
	}
</style>
