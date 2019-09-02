<template>
    <div class="header">
        <router-link to="/">Home</router-link>
        <router-link to="/admin">Admin</router-link>
    </div>
</template>

<script>
export default {
    name:'Header'

}
</script>

<style>
    @media screen and (max-width: 415px) {
        .header{
            background:rgb(241, 241, 241);
            width: 100%;
            height: 150px;

            padding: 0 30px 0 30px;

            border-top: 5px solid #FA749C;
            border-bottom: 1.5px solid #e4e4e4;
            
        }
    }
    
</style>
