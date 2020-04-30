<script>
	import TodoList from './TodoList.svelte';
	import TodoAdd from './TodoAdd.svelte';

	let myList = ["clean kitchen", "do 10,000 steps"];

	function addItem(item) {
		myList = [...myList,item]
	}
</script>

<main>
	<div class="title">My To Do List</div>
	{#if myList.length === 0}
	   <div>All done. Great!</div>
    {:else}
		<TodoList bind:todoItems={myList}/>
	{/if}
	<TodoAdd on:new-item-event={({detail}) => addItem(detail)}/>
	<TodoAdd on:new-item-event={({detail}) => addItem(detail)}/>
</main>


<style>
	.title {
		font-weight: bold;
		font-size: 14pt;
	}
</style>