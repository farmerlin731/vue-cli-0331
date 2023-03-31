<template>
<nav-bar/>
  <router-view />
</template>

<style lang="scss">
@import "./assets/stylesheet/all";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>


<script>
import NavBar from "./components/NavBar.vue";

export default {
  data(){
    return{}
  },
  components:{
    NavBar,
  }
}
</script>
