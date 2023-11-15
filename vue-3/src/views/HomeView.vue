<template>
  <div class="home">
    <h1>
      NEW<span style="color: purple; margin-reight: 5px">
        COLLECTION</span>  
    </h1>
    <displayProduct name="new" :product="product"></displayProduct>
    <h1>
      BEST<span style="color: purple; margin-reight: 5px"> SELLER</span>
    </h1>
    <displayProduct name="best" :product="product"></displayProduct>
    <h1 class="form">
      REVIEWS FROM
      <span style="color: purple; margin-reight: 5px">CUSTOMERS</span>
      <Reviews></Reviews>
    </h1>
  </div>
</template>

<script>
// @ is an alias to /src
import displayProduct from "../components/displayProduct.vue";
import Reviews from "../components/Reviews.vue";
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
    Reviews,
  },
};
</script>
