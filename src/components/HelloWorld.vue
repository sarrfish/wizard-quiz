<template>
  <h1>Wizarding World Quiz</h1>
  <div id="quiz">
    <!-- <button @click="getHouses">Start the Quiz!</button> -->
  </div>
  <button id="submit">Get Results</button>
  <div id="results"></div>

</template>

<script>
// eslint-disable-next-line 
const quizQuestions = [
  {
    question: "Which house has a lion for their emblem?",
    answers: {
      a: 'Gryffindor',
      b: 'Ravenclaw',
      c: 'Hufflepuff',
      d: 'Slytherin'
    },
    correctAnswer: 'a'
  },
  {
    question: "What color does Hufflepuff House wear?",
    answers: {
      a: 'red',
      b: 'blue',
      c: 'yellow',
      d: 'green'
    },
    correctAnswer: 'c'
  },
  {
    question: "Which founder was head of Ravenclaw?",
    answers: {
      a: 'Godric Gryffindor',
      b: 'Rowena Ravenclaw',
      c: 'Helga Hufflepuff',
      d: 'Salazar Slytherin'
    },
    correctAnswer: 'b'
  },
  {
    question: "Which ghost belongs to Slytherin House?",
    answers: {
      a: 'Nearly Headless Nick',
      b: 'The Grey Lady',
      c: 'The Fat Friar',
      d: 'The Bloody Barron'
    },
    correctAnswer: 'd'
  },
];

const baseUrl = 'https://wizard-world-api.herokuapp.com/';

export default {
  name: 'HelloWorld',
  methods: {
    getHouses() {
      let reqUrl = baseUrl + 'Houses';

      fetch(reqUrl)
        .then((response) => response.json())
        .then((data) => this.$emit('update:houses', data));
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
