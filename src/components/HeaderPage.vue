<template>
  <div class="inputs">
    <h1>{{ title }}</h1>
  </div>
</template>

<script>
export default {
  name: "HeaderPage",
  props: {
    title: {
      type: String,
      default: "",
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Kdam+Thmor+Pro&family=Quicksand:wght@300&display=swap");
h1 {
  font-family: "Quicksand", sans-serif;
}
</style>
