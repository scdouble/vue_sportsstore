<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col bg-dark text-white">
        <a class="navbar-brand">SPORTS STORE</a>
        <cart-summary />
      </div>
    </div>
    <div class="row">
      <div class="col-3 bg-info p-2">
        <CategoryControls />
      </div>
      <!-- <div class="col-9 bg-success p-2">
        <h4 class="text-white m-2">Products</h4>
      </div> -->
      <div class="col-9 p-2">
        <product-list />
      </div>
    </div>
  </div>
</template>

<script>
import ProductList from "./ProductList.vue";
import CategoryControls from "./CategoryControls";

import CartSummary from "./CartSummary.vue";
export default {
  components: { ProductList, CategoryControls, CartSummary },
};
</script>,
    CartSummary