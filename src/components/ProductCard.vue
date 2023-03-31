<template>
  <div class="card" style="width: 18rem">
    <div
      class="card-img-top"
      :style="{
        backgroundImage: `url(${item.imageUrl})`,
        height: `${height}px`,
      }"
      style="background-size: cover; background-position: center center"
    />
    <div class="card-body">
      <h5 class="card-title">{{ item.title }}</h5>
      <p class="card-text">
        {{item.description}}
      </p>
      <button class="btn btn-primary" @click="toProduct(item.id)">
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
      height: 300,
    };
  },
  methods: {
    toProduct(id) {
      console.log(id);
      this.$router.push(`/item/${id}`);
    },
  },
  props: ["outInfo"],
  mounted() {
    this.item = this.outInfo;
  },
};
</script>