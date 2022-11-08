<template>
  <HelloWorld v-model:houses="houses"/>
  <DisplayList :houses="houses"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import DisplayList from './components/DisplayList.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    DisplayList
  },
  data() {
    return {
      houses: []
    }
  },
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
