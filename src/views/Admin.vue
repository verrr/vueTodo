<template>
  <div id="app">
    <div class="editor-container">
      <AddTodo/>
      <FilterTodos/>
    </div>
    <Todos/>
  </div>
</template>

<script> 
import Todos from "../components/Todos.vue";
import AddTodo from "../components/AddTodo.vue";
import FilterTodos from '../components/FilterTodos.vue';


export default {
  name: 'Admin',
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

<style lang = "scss" scoped>
  .editor-container{
    background: rgb(241, 241, 241);
    width: 100%;
    height: 50px;
    padding:0 30px;

    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
 </style>
