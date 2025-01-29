<template>
  <main>
    <header>
      <h1 id="title">Quiz</h1>
      <input type="text" id="search-input" />
    </header>
    <section id="quis-container">
      <div class="card">
        <img
          src="https://plus.unsplash.com/premium_photo-1661882403999-46081e67c401?q=80&w=1729&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
          alt="img"
        />
        <div class="card-body">
          <h2>Programming</h2>
          <p>2 question</p>
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