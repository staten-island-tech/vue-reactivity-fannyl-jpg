<template>
  <!-- <h1 v-if="selected === 'A'">Correct Answer</h1>
  <h1 v-else-if="selected === ''">Select an asnwer</h1>
  <h1 v-else>"Wrong"</h1>
  <h1>{{ student }}</h1>
  <ul>
    <li v-for="animal in animals" :key="animal">{{ animal }}</li>
  </ul>
  <select v-model="selected">
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>{{ selected }}</span>
 -->
  <div class="home">
    <Button @button-click="bye">Button One</Button>
    <Button @button-click="hello">Button Two</Button>
    <Card title="Hello World" />
  </div>
</template>

<script>
/* import Button from "../components/TheButton.vue";
 */ import Card from "../components/TheCard.vue";

export default {
  name: "Home",
  components: {
    Button,
    Card,
  },
  data() {
    return {
      selected: "",
    };
  },
};

/* export default {
  data() {
    return {
      student: "Jason",
      animals: ["pig", "cow", "ostrich", "Zee"],
      graduated: true,
      selected: "",
    };
  },
  methods: {},
}; */

fetch("https://www.fruityvice.com/api/fruit/banana")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error(error));
</script>
