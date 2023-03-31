<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  methods: {
    getList() {
      this.axios.get("https://randomuser.me/api/").then((res) => {
        console.log(res.data);
      });
    },
  },
  mounted() {
    this.getList();
  },
};
</script>
