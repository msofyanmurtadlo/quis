<script setup>
import { defineProps } from "vue";
const { questionPage, barPercentage } = defineProps([
  "questionPage",
  "barPercentage",
]);
</script>
<template>
  <header>
    <h4>Questions {{ questionPage }}</h4>
    <div class="bar">
      <div class="bar-progrss" :style="{ width: barPercentage }"></div>
    </div>
  </header>
</template>
<style scoped>
header {
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
.bar {
  width: 100%;
  height: 10px;
  background-color: #f2f2f2;
  border-radius: 5px;
  overflow: hidden;
}
.bar-progrss {
  width: 0%;
  height: 100%;
  background-color: #4caf50;
}
</style>