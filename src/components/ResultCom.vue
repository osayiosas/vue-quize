<script setup>
import { defineProps } from 'vue'

import { RouterLink } from 'vue-router'

const { numberOfCorrcetAnswers, questionsLength } = defineProps([
  'questionsLength',
  'numberOfCorrcetAnswers'
])
</script>

<template>
  <div class="results">
    <p>Your Results...</p>
    <h1>{{ numberOfCorrcetAnswers }}/{{ questionsLength }}</h1>
    <RouterLink to="/" class="btn">Go to Home</RouterLink>
  </div>
</template>

<style scoped>
.results {
  text-align: center;
  padding: 100px 0;
}

p {
  font-size: 30px;
  font-weight: bold;
}
h1 {
  font-size: 100px;
  font-weight: bold;
  color: #ff0000;
}

.btn {
  display: inline-block;
  padding: 10px 20px;
  background-color: #ff0000;
  color: #fff;
  text-decoration: none;
  border-radius: 5px;
  margin-top: 20px;
  font-size: 20px;
}
</style>
