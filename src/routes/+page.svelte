<script>
    let todoItems = [];
    let newItem;

    function AddItem(){
        if (newItem != undefined){
            todoItems.push(newItem);
            console.log(todoItems);
        }
        todoItems = todoItems;
    }

    function RemoveItem(name){
        todoItems.splice(todoItems.indexOf(name), 1);
        todoItems = todoItems;
    }
</script>
<main>
    <h1>TODO</h1>
    <body>
        <div class="input">
            <button on:click={AddItem}>Add</button>
            <input type="text" id="newitem" bind:value={newItem}>
        </div>
        <div class="list">
            <ul>
                {#each todoItems as item}
                    <li>
                        {item}
                        <button on:click={RemoveItem(item)}>Remove</button>
                    </li>
                {/each}
            </ul>
        </div>
    </body>
</main>
<style>
    h1 {
        font-size: 50px;
        text-align: center;
    }

    ul {
        font-size: 30px;
    }

    .input {
        text-align: center;
    }
</style>