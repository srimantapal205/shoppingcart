<template>
  <div class="card p-2 mb-2">
    <div class="row">
    <div class="col-11">
      <div class="text-end">
        <h3>Cart Total: {{ cartTotalPrice.toFixed(2) }}</h3>
        <button type="button" class="btn btn-primary">Payment</button>
      </div>
    </div>
    <div class="col-1"></div>
</div>
  </div>
</template>

<script>
export default {
  name: "CartSummaryPrice",
  computed: {
    cartTotalPrice() {
      return this.$store.getters.cartTotalPrice;
    },
  },
};
</script>
