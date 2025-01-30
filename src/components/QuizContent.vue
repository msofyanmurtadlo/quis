<script setup>
import { defineProps } from "vue";
const { question } = defineProps(["question"]);
const emit = defineEmits(["selectedOption"]);
function emitSelectedOption(option) {
  emit("selectedOption", option);
}
</script>
<template>
  <section id="question-container">
    <h1 class="question-title">{{ question.text }}</h1>
  </section>
  <section id="options-container">
    <div
      class="option"
      v-for="option in question.answers"
      :key="option.id"
      @click="emitSelectedOption(option)"
    >
      <p class="option-label">{{ option.label }}</p>
      <div class="option-value">{{ option.text }}</div>
    </div>
  </section>
</template>
<style scoped>
#question-container {
  margin-bottom: 20px;
}
.question-title {
  font-size: 24px;
  font-weight: bold;
}
#options-container {
  display: flex;
  flex-direction: column;
}
.option {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}
.option-label {
  font-size: 20px;
  font-weight: bold;
  margin-right: 10px;
}
.option-value {
  width: 100%;
  padding: 10px;
  border-radius: 5px;
  background-color: #f2f2f2;
  align-items: center;
}
</style>