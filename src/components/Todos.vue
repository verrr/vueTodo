<template>
    <div>
        <h3>
            Todos
        </h3>
        <div class="todos">
            <div v-for='todo in allTodos' v-bind:key='todo.id' class="todo">
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
        ...mapActions(['fetchTodos', 'deleteTodo'])
    },
    computed: mapGetters(['allTodos']),
    created(){
        this.fetchTodos();
    }
}
</script>

<style scoped>

</style>
