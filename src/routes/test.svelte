<script lang="ts">
	// npm run dev -- --open
	import { count } from '../store.js';
	const greeting = `こんにちは`;
	let countValue: number;
	count.subscribe((value) => {
		countValue = value;
	});
</script>

<h1>TEST</h1>
<p>{greeting}</p>
<p>{countValue}</p>

<style>
	h1 {
		color: red;
	}
</style>
