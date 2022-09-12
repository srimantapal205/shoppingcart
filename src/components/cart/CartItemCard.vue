<template>
  <div class="card p-2 mb-2">
    <div class="row">
      <div class="col-1">
        <img :src="imagePath" :alt="cartProduct.name" width="70" />
      </div>
      <div class="col-2">{{ cartProduct.name }}</div>
      <div class="col-5 text-start">{{ desciption }}</div>
      <div class="col-1 text-center">&euro;{{ cartProduct.price }}</div>
      <div class="col-1">{{ cartProduct.quantity }}</div>
      <div class="col-1">&euro;{{ tiotalItemCost.toFixed(2) }}</div>
      <div class="col-1"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["cartProduct"],
  computed: {
    desciption() {
      return this.cartProduct.description.substring(0, 100);
    },
    tiotalItemCost() {
      return this.cartProduct.price * this.cartProduct.quantity;
    },

    imagePath() {
      return require(`@/assets//img/${this.cartProduct.image}`);
    },
  },
};
</script>

<style lang="scss" scoped></style>
