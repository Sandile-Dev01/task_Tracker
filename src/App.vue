<template>
  <div class="container">
    <Header />
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

*,
html {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body {
  font-family: "Nunito", sans-serif;
}

.container {
  max-width: 500px;
  min-height: 300px;
  border: 2px solid blue;
  padding: 1.5rem;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background-color: red;
  color: wheat;
}
</style>
