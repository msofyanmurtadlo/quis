<script setup>
import QuizContent from "@/components/QuizContent.vue";
import QuizHeader from "@/components/QuizHeader.vue";
import QuizResult from "@/components/QuizResult.vue";
import { useRoute } from "vue-router";
import quizes from "../data/quizes.json";
import { computed, ref, watch } from "vue";

const route = useRoute();
const quizid = parseInt(route.params.id);
const quiz = quizes.find((quiz) => quiz.id === quizid);
const currentQuestion = ref(0);

const numberOfCorrectAnswer = ref(0);

const showResult = ref(false);

const questionPage = computed(() => {
  return `${currentQuestion.value + 1}/${quiz.questions.length}`;
});

const barPercentage = computed(() => {
  return `${((currentQuestion.value + 1) / quiz.questions.length) * 100}%`;
});

function onSelectedoption(option) {
  if (option.correct) {
    numberOfCorrectAnswer.value++;
  }
  if (currentQuestion.value === quiz.questions.length - 1) {
    showResult.value = true;
    return;
  }
  currentQuestion.value++;
}
// Menggunakan Wathcer
// const questionPage = ref(
//   `${currentQuestion.value + 1}/${quiz.questions.length}`
// );
// watch(
//   () => currentQuestion.value,
//   () => {
//     questionPage.value = `${currentQuestion.value + 1}/${
//       quiz.questions.length
//     }`;
//   }
// );
</script>

<template>
  <QuizHeader :questionPage="questionPage" :barPercentage="barPercentage" />
  <QuizContent
    v-if="!showResult"
    :question="quiz.questions[currentQuestion]"
    @selectedOption="onSelectedoption"
  />
  <QuizResult
    v-else
    :quizLength="quiz.questions.length"
    :numberOfCorrectAnswer="numberOfCorrectAnswer"
  />
</template>
