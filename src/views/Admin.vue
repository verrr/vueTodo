<template>
  <div id="app">
    
    <Todos/>
  </div>
</template>

<script> 
import Todos from "../components/Todos.vue";
import AddTodo from "../components/AddTodo.vue";
import FilterTodos from '../components/FilterTodos.vue';


export default {
  name: 'home',
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
 
</style>
