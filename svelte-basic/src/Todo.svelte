<script>

const dispalyTodo = (todo) => {
  console.log('dispalyTodo', todo.todo_id)
  const todoList = document.querySelector('#todo-list')
  todoList.appendChild(createTodoItem(todo))
  createEditItem(todo)
}

const renderTodo = (todos) => {
  todos.forEach(todo => { // rendertodo function
    dispalyTodo(todo)
  })
}

// Get todos from DB and display
const intialize = async () => { // rename intialize
  const data = await getTodos()
  console.log('data', data)
  renderTodo(data)
}
	
</script>

<main>
	<h1>Hello !</h1>
    <div id="wrapper">
        <form id="add-todo">
            <input type="text" id='todoText' placeholder="Todo List..."/> 
            <button> Add  </button>
        </form>
        <div id="todo-list" >
        </div>
    </div>
    <div id="footer">
    </div>
</main>
