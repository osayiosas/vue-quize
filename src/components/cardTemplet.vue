<script setup>
import { defineProps } from 'vue';


const {quiz} = defineProps([
    'quiz'
])

</script>

<template>
    <div class="card">
        <img :src='quiz.img' alt="image" />
        <div class="card-text">
            <h2> {{ quiz.name }} </h2>
            <p>{{ quiz.questions.length }}</p>
        </div>
    </div>
</template>


<style scoped>

 .card {
    width: 310px;
    overflow: hidden;
    border-radius: 2%;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 35px;
    margin-right: 20px;
    cursor: pointer;
  }

  .card img {
    width: 100%;
    height: 190px;
    margin: 0;
    object-fit: cover;
  }

  .card-text {
    padding: 0 5px;
  }

  .card-text h2 {
    font-size: 1.5rem;
    margin: 10px 0;
  }

  .card-text p {
    font-size: 1rem;
    color: #333;
  }
</style>

