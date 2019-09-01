<template>
    <div>
        <h3>
            Todos
        </h3>
        
        <div class="todos">
            <div class="todo" v-for='todo in allTodos' v-bind:key='todo.id' @dblclick="onDblClick(todo)" >
                <div class="status">
                    <span v-if="!todo.completed" class="incomplete">Incomplete </span>
                    <span v-if="todo.completed" class="complete">Completed</span>
                </div>
                {{todo.title}}
                <input type="button" value="Remove" @click="deleteTodo(todo.id)"/>
            </div>
        </div>
    </div>
</template>

<script>
import {mapGetters, mapActions} from 'vuex';

export default {
    name: 'Todos',
    methods:{
        ...mapActions(['fetchTodos', 'deleteTodo', 'updateTodo']),
        onDblClick (todo){
            const updatedTodo ={
                id: todo.id,
                title: todo.title,
                completed: !todo.completed
            }
            this.updateTodo(updatedTodo);
        }
    },
    computed: mapGetters(['allTodos']),
    created(){
        this.fetchTodos();
    }
}
</script>

<style scoped>

</style>
