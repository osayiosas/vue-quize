<template>
    <div>
       <header>
        <h4>Question 1/3</h4>
        <div class="bar">
            <div class="completion"></div>
        </div>
       </header>
       <div>
        <div class="question-conatiner">
            <h1 class="question">
                What is the capital of Nigeria?
            </h1>
        </div>
        <div class="options-container">
            <div class="option">
                <input type="radio" name="option" id="option1">
                <label for="option1">Abuja</label>
            </div>
            <div class="option">
                <input type="radio" name="option" id="option2">
                <label for="option2">Lagos</label>
            </div>
            <div class="option">
                <input type="radio" name="option" id="option3">
                <label for="option3">Kano</label>
            </div>
            <div class="option">
                <input type="radio" name="option" id="option4">
                <label for="option4">Ibadan</label>
            </div>
        </div>
       </div>
    </div>
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
        width: 300px;
        height: 50px;
        border: 3px solid beige;
    }

    .completion {
        width: 0%;
        height: 100%;
        background: beige;
    }
</style>