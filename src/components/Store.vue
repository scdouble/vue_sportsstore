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
        <Search />
        <product-list />
      </div>
    </div>
  </div>
</template>

<script>
import ProductList from "./ProductList.vue";
import CategoryControls from "./CategoryControls";
import Search from "./Search";
import CartSummary from "./CartSummary.vue";
import { mapMutations } from "vuex";
export default {
  components: { ProductList, CategoryControls, CartSummary, Search },
  methods: {
    ...mapMutations(["setShowSearch"]),
  },
};
</script>,
    CartSummary