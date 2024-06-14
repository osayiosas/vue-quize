<script setup>
import cardTemplet from "./components/cardTemplet.vue";
  import q from "./data/quizes.json";

  import { ref, watch } from "vue";

  const quizes = ref(q)

  const search = ref('')

  watch(search, (val) => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(val.toLowerCase()))
  })

</script> 

<!-- template -->

<template>
  <div class="container">
    <header>
     <h1>Quize</h1>
       <input v-model.trim="search" type="text" placeholder="Search...">
    </header>
   
    <div class="options-container">

      <cardTemplet v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
    </div>
  </div>
</template>

<!-- style using the scoped -->

<style scoped>

  .container {
    max-width: 1000px;
    margin: 0 auto;
  }

  header {
    margin-bottom: 10px;
    margin-top: 30px;
    display: flex;
    align-items: center;
  }

  header h1 {
    font-weight: bold;
    margin-right: 30px;
  }

  header input {
    border: none;
    background: rgba(118, 128, 128, 0.1);
    padding: 10px;
    border-radius: 5px;
  }

  /* cards  */
  .options-container {
    display: flex;
    flex-wrap: wrap;
    margin-top: 40px;
  }
</style>


