<template>
  <HelloWorld :list="list" />
  <TheWelcome :list="list" />
</template>

<script>
export default {
  data() {
    return {
      list: ["Zee", "Ryan", "Katie"],
    };
  },
};
</script>

<style scoped></style>
