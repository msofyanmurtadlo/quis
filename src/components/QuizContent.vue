<template>
  <section id="question-container">
    <h1 class="question-title">Test</h1>
  </section>
  <section id="options-container">
    <div class="option">
      <p class="option-label">a</p>
      <div class="option-value">1</div>
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