<template>
 <ul>
    <li v-for="(house, index) in houses" v-bind:key="index">
        <h2>{{ house.name }}</h2>
    </li>
 </ul>
</template>

<script>
export default {
    name: 'DisplayList',
    props: ['houses']
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>