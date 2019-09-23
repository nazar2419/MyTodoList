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
@import url('https://use.fontawesome.com/releases/v5.7.2/css/all.css');

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  /*text-align: center;*/
  margin:60px auto;
  padding:2rem 3rem 3rem;
  max-width:500px;
  background:#006666;
  color:#FFF;

}

 
</style>
