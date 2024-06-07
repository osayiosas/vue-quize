<script setup>
  import q from "./data/quizes.json";
</script> 

<!-- template -->

<template>
  <div class="container">
    {{ q }}
    <header>
     <h1>Quize</h1>
       <input type="text" placeholder="Search...">
    </header>
   
    <div class="options-container">
      <div class="card">
        <img src="@/assets/math.jpeg" alt="">
        <div class="card-text">
          <h2>Math Quize</h2>
          <p>15 questions</p>
        </div>
      </div>
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


