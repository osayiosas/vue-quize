<script setup>
import { defineProps } from 'vue'

const { 
  questionStatus, 
  barPercentage 
} = defineProps(
  [
    'questionStatus', 
    'barPercentage'
  ]
  )
</script>

<template>
  <header>
    <h4>{{ questionStatus }}</h4>
    <div class="bar">
      <div class="completion" :style="{ width: barPercentage }"></div>
    </div>
  </header>
</template>

<style scoped>
header {
  margin-top: 20px;
}

header h4 {
  font-weight: bold;
  font-size: 40px;
}

.bar {
  width: 400px;
  height: 40px;
  border: 3px solid beige;
  border-radius: 15px;
}

.completion {
  width: 0%;
  height: 100%;
  background: rgb(235, 235, 177);
}
</style>
