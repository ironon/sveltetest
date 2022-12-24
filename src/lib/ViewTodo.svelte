<script lang="ts">
    export let todos: string[]
    function removeTodo(event, i:number) {
        todos.splice(i, 1)
        todos = todos
    }
</script>

<div id="viewtodo">
    {#each todos as todo, i}
        <div id="todo">
            <p>{todo}</p>
            <button id="remove" on:click={(event) => removeTodo(event, i)}>X</button>
        </div>
    {/each}
</div>

<style>
    #viewtodo {
        border: 1px solid black;
        margin-top: 1vh;
        min-height: 10%;
        padding-left: 1ch;
    }
    #todo {
        display: flex;
        flex-direction: row;
        justify-content: space-between; 
    }
    #remove {
        background-color: transparent;
        border: 0px;
        opacity: 0;
        width: 30%;
    }
    #remove:hover {
        background-color: transparent;
        border: 0px;
        opacity: 1;
    }
</style>