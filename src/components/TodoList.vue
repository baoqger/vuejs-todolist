<template>
  <div>
    <p>Completed Task: {{todos.filter( todo => {return todo.done === true}).length }}</p>
    <p>Pending Task: {{todos.filter( todo => {return todo.done === false }).length }}</p>
    <todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo"></todo>
  </div>
</template>

<script type = "text/javascript" >
import Todo from './Todo'

export default {
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
    deleteTodo (todo) {
      this.todos.splice(this.todos.indexOf(todo), 1)
    }
  }
}
</script>
<style>
p.tasks {
  text-align: center;
}
</style>
