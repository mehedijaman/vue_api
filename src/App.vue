<script setup>
import {ref} from 'vue'
import axios from 'axios'

const baseUrl = 'https://jsonplaceholder.typicode.com/posts'
const weatherData = ref('')

// async function getWeather(){
//   const data = await axios.get(baseUrl)
//   weatherData.value = data
// }

function getWeather(){
  axios.get(baseUrl)
  .then(res => {
    weatherData.value = res
  })
}

getWeather()
</script>

<template>
{{ weatherData.data }}
</template>
