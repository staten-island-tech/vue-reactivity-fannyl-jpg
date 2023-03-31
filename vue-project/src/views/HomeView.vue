<template>
  <div class="home"><</div>
</template>
<script>
import Button from "../components/ButtonButton.vue";
import Card from "../components/Card.vue";
export default {
  name: "Home",
  components: {
    Button,
    Card,
  },
  data() {
    return {
      slected: "",
    };
  },
  methods: {},
};
fetch("https://www.fruityvice.com/api/fruit/banana")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error(error));
</script>
