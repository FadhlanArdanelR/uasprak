<template>
  <div class="weather-widget">
    <h2>Weather Widget</h2>
    <div class="search-bar">
      <input v-model="city" placeholder="Enter city name" @keyup.enter="getWeather" />
      <button @click="getWeather">Search</button>
    </div>
    <div v-if="weather" class="weather-info">
      <div class="weather-item animate-item">
        <p class="bold-text"><strong>Location:</strong> {{ weather.name }}</p>
        
        <p class="bold-text"><strong>Temperature:</strong> {{ weather.main.temp }}°C</p>
        
        <p class="bold-text"><strong>Weather:</strong> {{ weather.weather[0].description }} </p>

      </div>
    </div>
    <div v-else>
      <p>Enter a city name to see the weather.</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import axios from 'axios'

const city = ref('')
const weather = ref(null)

const getWeather = async () => {
  const apiKey = 'ceb97d9ca273e7696ff7f99b1a1fa728'
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city.value}&units=metric&appid=${apiKey}`

  try {
    const response = await axios.get(url)
    weather.value = response.data
  } catch (error) {
    console.error(error)
    weather.value = null
  }
}
</script>

<style scoped>
.weather-widget {
  padding: 20px;
  border: 1px solid var(--medium-red);
  border-radius: 10px;
  max-width: 700px;
  margin: 100px auto 50px auto; 
  text-align: center;
  background-color:white;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.weather-widget h2 {
  color:black;
  font-size: 36px;
  font-weight: bold;
  margin-bottom: 20px;
}

.search-bar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.search-bar input {
  padding: 10px;
  width: 70%;
  margin-right: 10px;
  border: 1px solid black;
  border-radius: 5px;
}

.search-bar button {
  padding: 10px;
  border: 1px solid black;
  color: var(--light-beige);
  cursor: pointer;
  border-radius: 5px;
}

.search-bar button:hover {
  background-color: black;
  color:white;
  transition: 0.5s;
}

.weather-info {
  margin-top: 40px; 
  display: flex;
  justify-content: center; 
  align-items: center;
  flex-wrap: wrap; 
}

.weather-item {
  margin: 20px; 
  border-radius: 5px;
  padding: 20px;
  background-color:#686D76;
  text-align: center;
  width: 220px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  animation: backgroundColorChange 3s ease infinite; 
  color: white;
}

.weather-item img {
  margin-top: 10px;
  width: 35px;
  height: 35px;
}

.weather-item p {
  margin: 0;
  color: white;
  font-weight: bold; 
}

.weather-border {
  border-top: 1px solid white;
  margin-top: 10px;
  padding-top: 10px;
}



</style>
