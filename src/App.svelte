<script>
  import CreateTodo from '~/components/CreateTodo'
  import Todo from '~/components/Todo'
  import {todos} from '~/store'

  const storageTodos = localStorage.getItem('todos')
  if (storageTodos) {
    $todos = JSON.parse(storageTodos)
  }
</script>

<div class="container">
  <CreateTodo />
  <div class="todos">
    {#each $todos as todo (todo.id) }
    <Todo todo={todo} />
    {/each}
  </div>
</div>

<style lang="scss">
  .todos {
    padding: 20px 0;
  }
</style>