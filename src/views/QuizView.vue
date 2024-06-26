<script setup>
import { ref, watch, computed } from 'vue'
import QuestionsCom from '../components/QuestionsCom.vue'
import ResultCom from '../components/ResultCom.vue' 
import QuizHeader from '../components/QuizHeader.vue'
import { useRoute } from 'vue-router'
import quizes from '../data/quizes.json'

const route = useRoute()

const quizId = parseInt(route.params.id)

const quiz = quizes.find((q) => q.id == quizId)

const currentQuestionIndex = ref(0)
const numberOfCorrcetAnswers = ref(0)
const showResult = ref(false)

// const questionStatus = ref(`${currentQuestionIndex.value}/${quiz.questions.length}`)

// watch( () => currentQuestionIndex.value, () => {
//     questionStatus.value = `${currentQuestionIndex.value}/${quiz.questions.length}`
// })

const questionStatus = computed(() => `${currentQuestionIndex.value}/${quiz.questions.length}`)

const barPercentage = computed(
  () => `${(currentQuestionIndex.value / quiz.questions.length) * 100}%`
) 

const onOptionSelected = (isCorrect) => {
  if (isCorrect) {
    numberOfCorrcetAnswers.value++;
  }
  if(quiz.questions.length === currentQuestionIndex.value + 1) {
    showResult.value = true
  } else {
    currentQuestionIndex.value++;
  }
  currentQuestionIndex.value;
}
</script>
<template>
 <div>
     <QuizHeader :questionStatus="questionStatus" :barPercentage="barPercentage" />
     
        <QuestionsCom
         v-if="!showResult"
         :question="quiz.questions[currentQuestionIndex]" @selectOption="onOptionSelected" 
        />
        <ResultCom 
         v-else
           :questionsLength="quiz.questions.length"
           :numberOfCorrcetAnswers="numberOfCorrcetAnswers"
        />
 </div>
</template>
