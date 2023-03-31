<template>
  <div class="container" style="margin-top: 100px">
    <div class="row row-cols-4">
      <div class="col" v-for="item in products" :key="item.id">
        <cardTmp :outInfo="item"></cardTmp>
      </div>
    </div>
  </div>
</template>

<script>
import cardTmp from "../components/ProductCard.vue";

export default {
  data() {
    return {
      itemList: ["app", "boy", "cat", "dog", "egg"],
      products:[],
      height:300,
    };
  },
  methods: {
    getProducts() {
      console.log(this.axios);
      const url = `${process.env.VUE_APP_API}/api/${process.env.VUE_APP_PATH}/products/all`;
      this.axios
        .get(url)
        .then((res) => this.products = res.data.products)
        .catch((err) => console.log(err));
    },
  },
  components:{
    cardTmp,
  },
  mounted() {
    this.getProducts();
  },
};
</script>