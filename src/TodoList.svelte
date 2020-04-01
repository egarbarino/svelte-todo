<script>
	export let todoItems;
    function deleteItem(i) {
		todoItems.splice(i,1)
		todoItems = [...todoItems];
	}	
</script>

<main>
	<ul>
		{#each todoItems as item, i}
			<li> {item} [ <span class="link" on:click={() => deleteItem(i)}>delete</span> ]</li>
		{/each}
	</ul>
</main>

<style>
	.link {
		cursor: pointer; 
		color: blue;
	}
</style>