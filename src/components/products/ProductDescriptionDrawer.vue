<template>
  <div
    class="offcanvas offcanvas-start"
    tabindex="-1"
    id="offcanvasExample"
    aria-labelledby="offcanvasExampleLabel"
    :class="{ show: active }"
    @click="$emit('closeProdectDrawer')"
  >
    <div class="drawer" :class="{ show: active }">
      <div class="offcanvas-header">
        <h5 class="offcanvas-title" id="offcanvasExampleLabel">ProductDetails</h5>
        <button
          type="button"
          class="btn-close text-reset"
          @click="$emit('closeProdectDrawer')"
        ></button>
      </div>

      <div class="offcanvas-body" v-if="productDetails">
        <img alt="Vue logo" :src="imagePath" />
        <h5 class="card-title">{{ productDetails.name }}</h5>
        <h6 class="card-title">{{ productDetails.catagory }}</h6>
        <h5 class="card-title">&euro;{{ productDetails.price.toFixed(2) }}</h5>
        <p class="card-text">{{ productDetails.description }}</p>
        <div class="cartTotal" v-if="product_total">
          <h3>In Cart</h3>
          <h4>{{ product_total }}</h4>
        </div>
        <div class="btn-group" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-primary">Add +</button>
          <button type="button" class="btn btn-danger">Remove -</button>
        </div>
      </div>
    </div>
  </div>
  <div class="modal-backdrop" :class="{ show: active }"></div>
</template>

<script>
export default {
  name: "ProductDescription",
  props: ["productDetails", "active"],
  computed: {
    imagePath() {
      return require(`@/assets//img/${this.productDetails.image}`);
    },
    product_total() {
      return 5;
    },
  },
  methods: {
    test(e) {
        console.log(e)
    }
  },
};
</script>

<style lang="scss">
.offcanvas {
  z-index: 99999;
  &.offcanvas-start {
    &.show {
      width: 65vw;
    }
  }
}
.modal-backdrop {
  display: none;
  &.show {
    display: block;
    opacity: 0.5;
    z-index: 1;
  }
}
</style>
