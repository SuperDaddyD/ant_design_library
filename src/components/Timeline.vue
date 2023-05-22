<script setup>
import Container from "../components/Container.vue";
import Card from "./Card.vue";
</script>
<template>
  <Container>
    <div class="timeline-container">
      <Card />
    </div>
  </Container>
</template>
<style scoped>
.timeline-container {
  /* max-width: 450px;
  margin: 0 auto; */
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
