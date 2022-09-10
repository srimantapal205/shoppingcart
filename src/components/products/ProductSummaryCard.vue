<template>
  <div class="col col-sm-6 col-md-4 col-lg-3 ">
    <div class="card">
      <img alt="Vue logo" :src="imagePath" />
      <div class="card-body">
        <h5 class="card-title">{{ product.name }}</h5>
        <h6 class="card-title">{{ product.catagory }}</h6>
        <h5 class="card-title" v-if="product.currency == 'EUR'">
          &euro;{{ product.price }}
        </h5>
        <h5 class="card-title" v-if="product.currency == 'USD'">${{ product.price }}</h5>
        <p class="card-text">{{ description }}</p>
        <button
          class="viewProduct btn btn-primary"
          @click="$emit('viewProduct', product)"
        >
          View Product Details
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductSummaryCard",
  props: ["product"],
  computed: {
    description() {
      return this.product.description.substring(0, 100) + "...";
    },
    imagePath() {
      return require(`@/assets//img/${this.product.image}`);
    },
  },
  methods: {},
};
</script>

<style lang="scss" scoped></style>
