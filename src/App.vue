<template>
  <div id="app">
    <Header/>
    <router-view/>
  </div>
</template>

<script>
import Header from './components/layout/Header.vue';
export default {
  name:"app",
  components: {
    Header
  }
}
</script>


<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Roboto:300,400,500,700,900&display=swap');
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
    background: #FAFAFA;
  }

</style>