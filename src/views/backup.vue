<template>
  <div class="container" style="margin-top: 100px">
    <div class="row">
      <!-- <div class="col-3" v-for="item in itemList" :key="item"> -->
      <div class="col-3" v-for="item in products" :key="item.id">
        <div class="card" style="width: 18rem">
          <div class="card-img-top" :style="{backgroundImage: `url(${item.imageUrl})`,height:`${height}px`}" style="background-size:cover;
    background-position: center center;"/>
          <div class="card-body">
            <h5 class="card-title">{{ item.title }}</h5>
            <p class="card-text">
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </p>
            <button class="btn btn-primary" @click="tmpClick(item.title)"><i class="bi bi-airplane-engines-fill"></i>Go somewhere</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
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
    tmpClick(test){
      alert(test);
    }

  },
  mounted() {
    this.getProducts();
  },
};
</script>