<script setup>
 import cardTemplate from "../components/cardTemplet.vue";
  import q from "../data/quizes.json";

  import { ref, watch } from "vue";

  const quizes = ref(q)

  const search = ref('')

  watch(search, (val) => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(val.toLowerCase()))
  })

</script> 

<!-- template -->

<template>
  <div>
    <header>
     <h1>Quize</h1>
       <input v-model.trim="search" type="text" placeholder="Search...">
    </header>
   
    <div class="options-container">

      <cardTemplate v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
    </div>
  </div>
</template>

<!-- style using the scoped -->

<style scoped>
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


