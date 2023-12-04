<template>
  <div class="container">
    <Header 
    @toggle-add-todo="toggleAddTodo"
    title="Task Manager"
    :showAddTodos="showAddTodos"
     />
     <section class="main">
      <div v-if="showAddTodos">
      <AddTodo @save-todo="saveTodo"/>
    </div>
    <Todos @delete-todo="deleteTodo" :todos="todos" />
  </section>
</div>
</template>

<script>
import Header from './components/Header.vue';
import Todos from './components/Todos.vue';
import AddTodo from './components/AddTodo.vue';
export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [],
      showAddTodos: false,
    }
  },
  methods: {
    toggleAddTodo() {
      this.showAddTodos = !this.showAddTodos
    },
    saveTodo(todo) {
      this.todos = [...this.todos, todo]
    },
    deleteTodo(id) {
      if (confirm('Do you want to remove task?')) {
        this.todos = this.todos.filter((todo) => todo.id !== id)
      }
    }
  },
  mounted() {
    this.todos = [
      {
        id: 1,
        text: 'Read a book!',
        completed: false,
      }

    ]
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  max-width: 600px;
  margin: 8px auto;
  border: 1px solid #0097ee;
  border-radius: 4px;
  font-family: serif;
}
.main {
  padding: 12px;
}
</style>