<h1>Welcome to my Todo App</h1>

<script>
    let todos = [];
    function addTodo() {
        todos = [...todos, ''];
    }
    function removeTodo(index) {
        todos = [...todos.slice(0, index), ...todos.slice(index+1)];
    }
</script>

<!-- #ControlFlow -->
{#each todos as todo, index}
    <input bind:value={todos[index]}>
    <!-- #Reactive -->
    <button on:click={()=>removeTodo(index)}>X</button>
    <br>
{/each}

<!-- #Reactive -->
<button on:click={addTodo}>Add Todo</button>