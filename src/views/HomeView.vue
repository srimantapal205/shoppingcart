<template>
  <div class="home">
    <ProductDescriptionDrawer
      :productDetails="product"
      :active="active.productDrawer"
      v-on:closeProdectDrawer="closeDrawer"
    />
    <div class="container mt-5">
      <div class="row g-3">
        <ProductSummaryCard
          v-for="product in items"
          :key="product.id"
          :product="product"
          v-on:viewProduct="viewProductDetails($event)"
        />
      </div>
    </div>
  </div>
</template>

<script>
import items from "@/data/item.js";
import ProductSummaryCard from "@/components/products/ProductSummaryCard.vue";
import ProductDescriptionDrawer from "@/components/products/ProductDescriptionDrawer.vue";
export default {
  name: "HomeView",
  components: {
    ProductSummaryCard,
    ProductDescriptionDrawer,
  },
  data() {
    return {
      items: items,
      product: null,
      active: {
        productDrawer: false,
      },
    };
  },
  methods: {
    viewProductDetails(product) {
      this.product = product;
      this.active.productDrawer = true;
      console.log(this.product);
    },
  },
  closeDrawer(e) {
    console.log(e)
  },
};
</script>
