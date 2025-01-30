<script setup>
import { defineProps } from "vue";
const { quizLength, numberOfCorrectAnswer } = defineProps([
  "quizLength",
  "numberOfCorrectAnswer",
]);
</script>

<template>
  <section>
    <p>Score:</p>
    <h1>{{ numberOfCorrectAnswer }}/{{ quizLength }}</h1>
    <RouterLink to="/">Go back</RouterLink>
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100vh;
}
h1 {
  font-size: 50px;
  margin: 20px 0;
}
p {
  font-size: 20px;
}
</style>