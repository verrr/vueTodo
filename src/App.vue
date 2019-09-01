<template>
  <div id="app">
    <AddTodo/>
    <FilterTodos/>
    <Todos/>
  </div>
</template>

<script> 
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo.vue";
import FilterTodos from './components/FilterTodos.vue'


export default {
  name: 'app',
  components: {
    Todos,
    AddTodo,
    FilterTodos
  },
  data(){
    return{
      msg: 'hi'
    }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
