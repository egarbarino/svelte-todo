<script>

    import { createEventDispatcher } from 'svelte'
    const dispatch = createEventDispatcher();

    let item = ""
    function add() {
	   dispatch("new-item-event",item);
	   item = ""
    }
</script>

<main>
<input type="text" id="description" bind:value={item}/>
<button type="button" on:click={add}>Add</button> 

</main>
