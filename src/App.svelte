<script lang="ts">
import AddTodo from "./lib/AddTodo.svelte";
import ViewTodo from "./lib/ViewTodo.svelte";
let todos: string[] = []
function todoAdded(todo) {
  todos = [...todos, todo]
}
</script>

<div id="todoapp">
  <h1>DAVID TODOSD </h1>
  <AddTodo todoAdded={todoAdded}/>
  <ViewTodo bind:todos={todos}/>
</div>

<style>
  
  #todoapp {
    display: flex;
    flex-direction: column;
  }
</style>