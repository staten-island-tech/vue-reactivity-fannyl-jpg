<template>
  <div class="card">
    <h2>{{ title }}</h2>
    <img src="" alt="" />
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    title: String,
    description: String,
    image: String,
  },
};
</script>

<style lang="scss" scoped></style>

<style>
.card {
  width: 30%;
  background-color: red;
  height: 500px;
  margin: 10px a;
}
</style>
