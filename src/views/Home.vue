<template>
    <div class="home-container">
        <h1>{{title}}</h1>
        <h2>{{body}}</h2>
        <h3>Fetched {{allTodos.length}} Todos</h3>
    </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
name:'Home',
data(){
    return{
        ...mapActions(["fetchTodos"]),
        title:'Todo Demo',
        body:'List, add, sort and remove todos'
    }
},
computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  }
}
</script>

<style lang="scss" scoped>
    .home-container{
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        padding: 40px 30px 0 30px; 
        *{
            font-family: 'Roboto', sans-serif;

        }
        h2{
            font-size: 16px;
            font-weight: 300;
        }
        h3{
            margin-top: 5px;
        }
    }
</style>
