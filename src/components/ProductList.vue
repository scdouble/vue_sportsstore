<template>
  <div>
    <div v-for="p in products" v-bind:key="p.id" class="card m-1 p-1 bg-light">
      <h4>
        {{ p.name }}
        <span class="badge badge-pill badge-primary float-right">
          {{ p.price | currency }}
        </span>
      </h4>
      <div class="card-text bg-white p-1">
        {{ p.description }}
        <button
          class="btn btn-success btn-sm float-right"
          v-on:click="handleProductAdd(p)"
        >
          Add To Cart
        </button>
      </div>
    </div>
    <page-controls />
  </div>
</template>

<script>
import { mapGetters, mapMutations } from "vuex";
import PageControls from "./PageControls.vue";
export default {
  components: { PageControls },
  computed: {
    //mapGetters helper function allows me to specify that
    //the processedProducts getter will be mapped using the name products
    ...mapGetters({ products: "processedProducts" }),
  },
  //filters, which are functions that are used to format data values
  filters: {
    currency(value) {
      return new Intl.NumberFormat("en-US", {
        style: "currency",
        currency: "USD",
      }).format(value);
    },
  },
  methods: {
    ...mapMutations({ addProduct: "cart/addProduct" }),
    handleProductAdd(product) {
      this.addProduct(product);
      this.$router.push("/cart");
    },
  },
};
</script>
