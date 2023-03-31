<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/hextest">HexTest</router-link> |
    <!-- <router-link :to="linkID">IDKHAHA</router-link> -->
    <router-link :to="`/item/${tmp}`">IDKHAHA</router-link>
  </div>
</template>
<style lang="scss">
#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>>

<script>
export default {
  data(){
    return{
      linkID:"/item/-MzuWU01NtAUqy9zGWYS",
      tmp:"-MzuWU01NtAUqy9zGWYS",
    }
  }
}
</script>

