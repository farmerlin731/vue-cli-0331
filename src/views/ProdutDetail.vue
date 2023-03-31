<template>
  <div class="card" style="width: 18rem">
    <div
      class="card-img-top"
      :style="{
        backgroundImage: `url(${item.imageUrl})`,
      }"
      style="
        height: 300px;
        background-size: cover;
        background-position: center center;
      "
    />
    <div class="card-body">
      <h5 class="card-title">{{ item.title }}</h5>
      <p class="card-text">
        {{ item.description }}
      </p>
      <button class="btn btn-primary" @click="toProduct(item.title)">
        <i class="bi bi-airplane-engines-fill"></i>Go somewhere
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      item: {},
    };
  },
  methods: {
    //-MzuWU01NtAUqy9zGWYS
    getData() {
      const { id } = this.$route.params;
        const url = `${process.env.VUE_APP_API}/api/${process.env.VUE_APP_PATH}/product/${id}`;
        this.axios.get(url).then((res) => (this.item = res.data.product));
    },
  },
  mounted() {
    this.getData();
  },
};
</script>