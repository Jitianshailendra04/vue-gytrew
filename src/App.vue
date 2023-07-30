<template>
  <div class="container">
    <h1 class="heading">Compute Product</h1>
    <img class="image" src="https://cdn.theforage.com/vinternships/companyassets/ay2tsYxaTif7Nt6z7/AA4Bnq2tJHALwE8cg/1680718790218/pexels-photo-14197334.jpeg" alt="Image Description" />
    
    <div v-if="showComputeButton" class="input-section">
      <label for="number1">Number 1:</label>
      <input type="number" v-model="number1" id="number1" />
      
      <label for="number2">Number 2:</label>
      <input type="number" v-model="number2" id="number2" />
      
      <button class="compute-button" @click="computeProduct">Compute</button>
    </div>
    
    <p v-else class="result-text">Product of {{ number1 }} and {{ number2 }} is: {{ product }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      product: 0,
      showComputeButton: true,
    };
  },
  methods: {
    computeProduct() {
      this.product = this.number1 * this.number2;
      this.showComputeButton = false;
    },
  },
};
</script>

<style>
.container {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  text-align: center;
  font-family: Arial, sans-serif;
  background-color: #f9f9f9;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.heading {
  font-size: 24px;
  margin-bottom: 10px;
}

.image {
  max-width: 100%;
  margin-bottom: 20px;
}

.input-section {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
  
.compute-button {
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.compute-button:hover {
  background-color: #0056b3;
}

.result-text {
  font-size: 18px;
  font-weight: bold;
}
</style>
