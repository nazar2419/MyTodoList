<template>
  <div id = "app">
    <h1>Todo Aplication</h1>
    <hr>
   <todo-list/>
  </div>
</template>

<script>
import  TodoList from './views/TodoList'

export default {
  name: 'app',
  components: {
    TodoList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  text-align: center;
  margin-top: 60px;
}
</style>
