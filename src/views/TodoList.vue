<template>

   <div class="todo-container">

     <div class="todo">
    <div class="row">
      <div class="col-12 py-5">
        <h1>{{ listName }}</h1>

        <!-- call page CreateTodo -->
         <create-todo @on-new-todo="addTodo($event)" />
        

      <div class="todo-lists">
        <ul class="todo-list">

        <!-- call page Todo -->
          <todo
            v-for="(todo, index) in todos"
            :key="index"
            :description="todo.description"
            :completed="todo.completed"

            @on-toggle="toggleTodo(todo)"
            @on-delete="deleteTodo(todo)"
            @on-edit="editTodo(todo, $event)"
          />
        </ul>
    
      </div>
      </div>
    </div>

     </div>
  </div>

</template>

<script>

import Todo from "./Todo.vue";
import CreateTodo from "./CreateTodo.vue";

export default {
   props: {
    listName: String,
    },
    data() {
      return {
        todos: [
          { description: "Project Hello world", completed: false },
          { description: "Project API", completed: false },
        ],
      };
    },
    methods: {
      addTodo(newTodo) {
        this.todos.push({ description: newTodo, completed: false });
      },
      toggleTodo(todo) {
        todo.completed = !todo.completed;
      },
      deleteTodo(deletedTodo) {
        this.todos = this.todos.filter(todo => todo !== deletedTodo);
      },
      editTodo(todo, newTodoDescription) {
        todo.description = newTodoDescription;
      },
    },
    
  components: { Todo, CreateTodo },
}
</script>

<style scoped src="@/assets/css/style.css">
  /* @import './assets/css/style.css'; */
</style>