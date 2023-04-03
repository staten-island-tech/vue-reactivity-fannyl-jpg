<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
import Products from "./components/ShoppingProducts.vue";
import Cart from "./components/ShoppingCart.vue";
</script>

<template>
  <div>
    <header>
      <button v-on:click="navigateTo('products')">View products</button>
      {{ cart.length }} in cart
      <button v-on:click="navigateTo('cart')">View Cart</button>
    </header>

    <div v-if="page === 'cart'">
      <Cart v-on:removeItemFromCart="removeItemFromCart" :cart="cart" />
    </div>

    <div v-if="page === 'products'">
      <Products v-on:addItemToCart="addItemToCart" />
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => {
    return {
      page: "products",
      cart: []
    };
  },
  methods: {
    addItemToCart(product) {
      this.cart.push(product);
    },
    removeItemFromCart(product) {
      this.cart.splice(this.cart.indexOf(product), 1);
    },
    navigateTo(page) {
      this.page = page;
    }
  },
  components: { Products, Cart }
};
</script>

<style>
body {
  margin: 0;
}
.products {
  display: grid;
  grid-template-columns: 1fr 1fr;
  display: padding;
}
.products button {
  padding: 10px;
  background-color: #fff;
  color: #000;
  outline: none;
  border: none;
  cursor: pointer;
}
</style>

<style scoped>
header {
  height: 90px;
  width: 1180px;
  background-color: #ffffe0;
  text-align: right;
  font-size: 30px;
  padding-top: 0px;
}
header button {
  padding: 15px;
  border: none;
  cursor: pointer;
  color: #000;
  background-color: #bee1e6;
}

</style>