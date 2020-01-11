<template>
  <div class="card">
    <span class="name">{{ card.name }}</span>
  </div>
</template>

<script>
export default {
  name: "recipe-card",
  props: ["card"]
};
</script>

<style></style>
