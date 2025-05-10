<script>
  import { useTodoState } from "$lib/states/todoState.svelte.js";
  import Todos from "$lib/components/Todos.svelte";
  import TodoForm from "$lib/components/TodoForm.svelte";
  import TodoItem from "$lib/components/TodoItem.svelte";

  let todoState = useTodoState();
</script>

<Todos>
  <span slot="form">
    <TodoForm />
  </span>
  <span slot="list">
    {#each todoState.todos as todo}
      <li>
        <TodoItem {todo} />
      </li>
    {/each}
  </span>
</Todos>