<template>
  <div class="container">
    <a target="_blank" rel="noopener noreferrer" href="https://github.com/giriss/todo-vue">→ View code on GitHub</a>
    <h1>Vue Todo App</h1>
    <TodoAdder @add="addTodo" />
    <TodoList :items="todos" @toggle="toggleTodo" @delete="deleteTodo" />
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import TodoAdder from './components/TodoAdder';

export default {
  name: 'todoApp',
  components: { TodoList, TodoAdder },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    addTodo(title) {
      this.todos = [...this.todos, { title }]
    },
    toggleTodo(title) {
      const index = this.todos.findIndex((todo) => todo.title === title);
      this.todos[index].completed = !this.todos[index].completed;
      this.todos = [...this.todos];
    },
    deleteTodo(title) {
      this.todos = this.todos.filter((todo) => todo.title !== title);
    }
  }
}
</script>

<style>
  body {
    padding: 8px;
  }
</style>
