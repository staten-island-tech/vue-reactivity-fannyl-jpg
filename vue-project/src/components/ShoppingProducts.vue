<template>
  <div>
    <h1>Products</h1>
    <div class="products">
      <div v-for="(product, index) in products" :key="index">
        <h3>{{ product.name }}</h3>
        <div class="cost">{{ product.cost }}</div>
        <img :src="product.image" />
        <button v-on:click="addItemToCart(product)">Add to cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      products: [
        {
          name: "Italian Red Meat Flavored Chips",
          cost: "$0.99",
          image:
            "lays.png"
        },
         {
          name: "Cucumber Flavored Chips",
          cost: "$0.99",
          image:
            "lays2.png"
        },
         {
          name: "Spicy Crayfish Flavored Chips",
          cost: "$0.99",
          image:
            "lays3.png"
        },
        {
          name: "Gudetama Potato Chips",
          cost: "$5.99",
          image:
            "gudetama.png",
        },
        {
          name: "Hello Kitty BBQ Chips",
          cost: "$5.99",
          image:
            "hk.png",
        },
        {
          name: "Naruto Scrambled Eggs Potato Chips",
          cost: "$5.99",
          image:
            "naruto.png",
        },
      ],
    };
  },
  methods: {
    addItemToCart(product) {
      this.$emit("addItemToCart", product);
    },
  },
};
</script>

<style></style>
