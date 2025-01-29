<script setup>

import { ref, watch } from 'vue';
import srcQuiz from './data/quizes.json';

const quizes = ref(srcQuiz);
const search = ref('');

watch(search, () => {
	quizes.value = srcQuiz.filter((quiz) => {
		return quiz.title.toLowerCase().includes(search.value.toLowerCase());
	});
});


</script>

<template>
  <main>
    <header>
      <h1 id="title">Quiz</h1>
      <input v-model.trim="search" type="text" id="search-input" />
    </header>
    <section id="quis-container">
      <div v-for="quiz in quizes" :key="quiz.id" class="card">
        <img
          :src="quiz.img"
          alt="img"
        />
        <div class="card-body">
          <h2>{{ quiz.title }}</h2>
          <p>{{ quiz.questions.length }} Questions</p>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
main {
  max-width: 800px;
  margin: auto;
}
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

.card {
  width: 270px;
  margin-right: 20px;
  margin-bottom: 20px;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  margin: 0;
}

.card-body {
  padding: 0 20px;
}

.card-body h2 {
  font-size: 20px;
  font-weight: bold;
}
</style>