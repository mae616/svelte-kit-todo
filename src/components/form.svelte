<script lang="ts">
let value:string;
export let addTodo: (value:string) => void;
</script>

<h1>form</h1>
<input bind:value />
<button on:click={()=>{
  addTodo(value);
}}>追加</button>
