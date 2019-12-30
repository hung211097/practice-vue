<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <ToDoList v-bind:todos="todos"/>
    <CreateTodo @add-todo="addTodo"/>
  </div>
</template>

<script>
import ToDoList from './components/ToDoList.vue'
import CreateTodo from './components/CreateTodo.vue'

export default {
  name: 'app',
  components: {
    ToDoList,
    CreateTodo
  },
  methods: {
    addTodo(todo) {
      this.todos.push({
        title: todo.title,
        project: todo.project,
        done: false,
      });
    },
  },
  data() {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
