<template>
    <div class="home">
        <h1>
          All <span style="color: darkgoldenrod; margin-reight: 5px">
            COLLECTION</span>
        </h1>
        <displayProduct name="" :product="product"></displayProduct>
      </div>
</template>

<script>
// @ is an alias to /src
import displayProduct from "../components/displayProduct.vue";
import products from "../assets/products.json"
export default {
  name: "HomeView",
  data() {
    return {
      product: products,
    };
  },
  components: {
    displayProduct,
  },
};
</script>
