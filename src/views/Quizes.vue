<script setup>
import { ref, watch } from "vue";
import srcQuiz from "../data/quizes.json";

import QuizCard from "../components/QuizCard.vue";

const quizes = ref(srcQuiz);
const search = ref("");

watch(search, () => {
  quizes.value = srcQuiz.filter((quiz) => {
    return quiz.title.toLowerCase().includes(search.value.toLowerCase());
  });
});
</script>

<template>
  <header>
    <h1 id="title">Quiz</h1>
    <input v-model.trim="search" type="text" id="search-input" />
  </header>
  <section id="quis-container">
    <QuizCard v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
  </section>
</template>

<style scoped>
header {
  margin-top: 30px;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
}
#title {
  font-weight: bold;
  margin-right: 30px;
}
#search-input {
  padding: 10px;
  border: none;
  border-radius: 5px;
  width: 200px;
  background-color: #f2f2f2;
}

#quis-container {
  display: flex;
  flex-wrap: wrap;
  margin-top: 20px;
}
</style>