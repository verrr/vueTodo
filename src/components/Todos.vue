<template>
  <div>
    <div class="todos">
      <div v-for="todo in allTodos" :key="todo.id" v-bind:class="{'complete':todo.completed, 'incomplete':!todo.completed, 'todo':true}" @dblclick="onDblClick(todo)">
        <div class="todo-details">
            <p class="title">{{todo.title}}</p>
            <div class="location">
                <img src="../assets/map.svg" alt="">
                <p>location</p>
            </div>
        </div>
        <div class="remove-btn" @click="deleteTodo(todo.id)">x</div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "Todos",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDblClick(todo) {
      const updatedTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      };
      this.updateTodo(updatedTodo);
    }
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  }
};
</script>

<style lang='scss' scoped>


    .todos {
    background: rgb(241, 241, 241);
    width: 100%;
    height: fit-content;
    padding: 20px 30px 0 30px;
    
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: flex-start;
    align-items: center;
    }
    .todo{
        cursor: pointer;
        background: #FFFFFF;
        width: 100%;
        height: 120px;
        margin: 10px 0 10px 0;   
        padding: 20px;

        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        
        &.complete{
            border-left: 4.5px solid green;
            border-top-left-radius: 4px;
            border-bottom-left-radius: 4px;
        }
        &.incomplete{
            @extend .complete;
            border-left: 4.5px solid #FA749C;

        }
       box-shadow: 0px 10px 23px -12px rgba(184,184,184, 1);



        .title{
            width:fit-content;
            font-family: 'Roboto', sans-serif;
            font-weight: 700;   
            font-size: 1em;
            &::first-letter{
                text-transform: capitalize;
            }

            color: #929292;         
        }
        .location{
            @extend .title;
            width: fit-content;
            min-width: 100px;
            display: flex;
            justify-content: flex-start;

            align-items: center;
            font-weight: 500;
            font-size: 0.9em;

            text-transform: capitalize;
            p{
                margin-left: 10px;
                color: #000;
            }
            
        }
        .remove-btn{
            display: flex;
            justify-content: center;
            align-items: center;
            
            width: 25px;
            min-width: 25px;
            height: 25px;

            border: 1.5px solid #bdbdbd;
            color: #bdbdbd;
            border-radius: 25px;

            text-transform: uppercase;
            font-size:12px;

            &:hover{
                color: #FA749C;
                border-color: #FA749C;
                transition: ease 300ms
            }
            
            

        }
    }
</style>
