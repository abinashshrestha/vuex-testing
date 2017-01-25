<template>
  <div id="app" class="container">
    <CompletedTodos></CompletedTodos>
    <GetTodo></GetTodo>
    <CurrentTodos></CurrentTodos>
  </div>
</template>

<script>
  import GetTodo from './components/GetTodo.vue'
  import CompletedTodos from './components/CompletedTodos.vue'
  import CurrentTodos from './components/CurrentTodos.vue'

export default {
    components: {
        GetTodo,
        CompletedTodos,
        CurrentTodos
    }
}
</script>

<style>
  @import '../node_modules/bootstrap/dist/css/bootstrap.min.css';
</style>
