<template>
    <div>
        <div class="add">
            <form action="" @submit="onSubmit">
                <input type="text" v-model="title" placeholder="ADD TODO...">
                <input type="submit" value="Add">
            
            </form>
        </div>
    </div>
</template>

<script>
import {mapActions} from 'vuex';
export default {
    name : 'AddTodo',
    data(){
        return{
            title:'',
            completed:false
        }
    },
    methods: {
        ...mapActions(['addTodo']),
        onSubmit(e){
            e.preventDefault();
            this.addTodo(this.title);
        }
    }
}
</script>

<style lang="scss" scoped>
    .add{
        *{
            font-family: 'Roboto', sans-serif;
            display: flex;
            flex-direction: row;
            justify-content: center;
            align-items: center;
        }
    }
    form{
        
        input[type='text']{
            
            padding: 10px 10px 8px 10px;
            border: 1px solid grey;

        }
        input[type ='submit']{
            appearance: none;
            padding: 10px 10px 8px 10px;
            margin-left: 5px;
            background: white;
            border: 1px solid grey;
            color: #929292;
            text-transform: uppercase;

            cursor: pointer;
        }
    }
</style>
