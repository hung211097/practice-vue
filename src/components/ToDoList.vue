<template lang="html">
  <div class="">
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <ToDo v-for="(todo, index) in todos" @delete-todo="deleteTodo" @complete-todo="completeTodo" v-bind:todo="todo" v-bind:key="index"/>
  </div>
</template>

<script>
import ToDo from './ToDo.vue'

export default {
  props: ['todos'],
  components: {
    ToDo
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    },
  }
}
</script>

<style lang="css" scoped>
</style>
