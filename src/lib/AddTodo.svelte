<script lang="ts">
    export let todoAdded: (s:string) => void;
    let value = ""
    function addTodo() {
        if (value == "") {
            return
        }
        todoAdded(value)
        value = ""
    }
    function onInput() {
        value = this.value
        
    }
    function keypress(e: KeyboardEvent) {
        if (e.key == "Enter") {
            value = this.value
            addTodo()
        }
    }
</script>

<div id="addtodo">
    <p>add ur todos or smth</p>
    <input on:change={onInput} on:keydown={keypress} {value}>
    <button on:click={addTodo}>ADD</button>
</div>

<style>
    #addtodo {
        
    }
</style>