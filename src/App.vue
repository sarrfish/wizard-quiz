<template>
  <DisplayQuiz :apiData="apiData"/>
</template>

<script>
import DisplayQuiz from './components/DisplayQuiz.vue'

const baseUrl = 'https://wizard-world-api.herokuapp.com/';

export default {
  name: 'App',
  components: {
    DisplayQuiz
  },
  data() {
    return {
      apiData: {}
    }
  },
  mounted() {
    let reqUrl = baseUrl + 'Houses';

    fetch(reqUrl)
      .then((response) => response.json())
      .then((data) => this.apiData = data);    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
