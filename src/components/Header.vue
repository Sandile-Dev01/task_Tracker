<template>
  <header>
    <h1>Task Tracker</h1>
    <Button />
  </header>
</template>

<script>
import Button from "./Button.vue";

export default {
  name: "Header",
  components: { Button },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
  align-items: center;
  margin-bottom: 20px;
}
</style>
