<template>
  <h1>Cart Details</h1>
  <div class="CartDetailSection">
    <!-- <div v-for="item in items" :key="item.id">
  {{item}}
  </div> -->
    <div class="container-fluid">
      <div class="card p-2 mb-2">
        <div class="row">
          <div class="col-1">Image</div>
          <div class="col-2">Product Name</div>
          <div class="col-5 text-start">Description</div>
          <div class="col-1 text-center">Price</div>
          <div class="col-1">Quantity</div>
          <div class="col-1">Item Total Price</div>
          <div class="col-1"></div>
        </div>
      </div>
      <CartItemCard
        v-for="product in products"
        :key="product.id"
        :cartProduct="product"
      /><CartSummaryPrice />
    </div>
  </div>
</template>

<script>
import CartItemCard from "@/components/cart/CartItemCard.vue";
import CartSummaryPrice from "@/components/cart/CartSummaryPrice.vue";

export default {
  name: "CartDetail",
  components: {
    CartItemCard,
    CartSummaryPrice,
  },
  computed: {
    products() {
      return this.$store.getters.cartItems;
    },
  },
};
</script>

<style lang="scss" scoped></style>
