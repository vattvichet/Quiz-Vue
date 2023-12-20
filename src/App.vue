<script setup>
import { ref } from "vue";
import q from "../src/data/quiz.json";

const quizes = ref(q);
</script>

<template>
  <div class="container">
    <header>
      <h1>Quiz</h1>
      <input type="text" placeholder="search..." />
    </header>
    <div class="option-container">
      <div class="card" v-for="quiz in quizes" :key="quiz.id">
        <img :src="quiz.img" alt="" />
        <div class="card-text">
          <h2>{{ quiz.name }}</h2>
          <p>{{ quiz.questions.length }} Questions</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scooped>
.container {
  max-width: 1000px;
  margin: auto;
}

header {
  margin-top: 30px;
  margin-bottom: 10px;
  display: flex;
  flex-direction: row;
  align-items: center;
}

header h1 {
  font-weight: bold;
  margin-right: 30px;
}

header input {
  padding: 10px;
  border-radius: 5px;
  border: none;
}

.option-container {
  display: flex;
  flex-wrap: wrap; /* Allow items to wrap to the next line */
  justify-content: space-between;
  border-radius: 2%;
}

.card {
  width: 30%;
  margin-top: 25px;
  background-color: rgb(255, 255, 197);
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 0px 0px 5px 5px rgba(238, 238, 238, 0.1);
  cursor: pointer;
  transition: transform 0.2s;
}

.card:hover {
  transform: scale(1.075);
}

.card img {
  border-radius: 2%;
  height: 190px;
  width: 100%;
}

.card-text {
  margin-left: 10px;
  margin-bottom: 10px;
  color: black;
}

.card-text h2 {
  font-weight: bold;
}
</style>
