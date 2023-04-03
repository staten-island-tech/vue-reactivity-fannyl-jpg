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
      cart: [],
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
    },
  },
  components: { Products, Cart },
};
</script>

<style>
body {
  margin: 0;
}
.products {
  display: grid;
  display: flex;
}
.products button {
  padding: 100px;
  background-color: black;
  color: white;
  outline: none;
  border: none;
  cursor: pointer;
}
</style>

<style scoped>
header {
   margin: 10px;
  padding: 20px;
  box-shadow: 2px 2px 5px blue;
  background-color: pink;
  text-align: right;
  font-size: 30px;
  padding-top: 0px;
}
header button {
  padding: 15px;
  border: none;
  cursor: pointer;
  color: white;
  background-color: green;
}
</style>

@media only screen and (max-width: 812px) {
  .col {
    max-width: 100%;
    flex: 100%;
    margin-top: 10% ;
  }
  
  #image {
    padding: 10px auto;
    margin: auto;
    border-radius: 30px;
    width: 914px;
    height: 610px;
    align-items: center;
    display: block;
    flex-wrap: wrap;
    max-width: 100%;
  }
}  

@media only screen and (min-device-width: 768px) {
  .col {
    margin: auto;
    padding: 5px 5px;
    background: #D4D5D3;
    box-shadow: 10px 10px 5px #555756;
    width: 25%;
    font-size: .5rem;
    flex: 50%;
    max-width: 40%;
    margin-top:50 px;
    flex-direction: column;
  }
  
  #image {
    padding: 10px auto;
    margin: auto;
    border-radius: 30px;
    width: 914px;
    height: 610px;
    align-items: center;
    display: block;
    flex-wrap: wrap;
    max-width: 100%;
  }
}

  @media screen and (min-device-width: 1200px) {
    .col {
      margin: auto;
      padding: 5px 5px;
      background: #D4D5D3;
      box-shadow: 10px 10px 5px #555756;
      width: 20%;
      font-size: .5rem;
      flex: 25%;
      max-width: 25%;
      margin-top: 20 px;
      flex-direction: column;
    }
    
    #image {
      padding: 10px auto;
      margin: auto;
      border-radius: 30px;
      width: 914px;
      height: 610px;
      align-items: center;
      display: block;
      flex-wrap: wrap;
      max-width: 100%;
    }
  }
