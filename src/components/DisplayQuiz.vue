<template>
  <form>
    <fieldset v-for="(question, index) in quizQuestions" v-bind:key="index">
      <h2>{{ question.text }}</h2>
      <div v-for="(house, h, index) in houses" v-bind:key="index">
        <input type="radio" :name="question.topic" :value="h" :id="h" />
        <label :for="h">{{ house[question.topic] }}</label>
      </div>
    </fieldset>
    <button @click="gradeQuiz">Computo resultum</button>
  </form>
</template>

<script>

export default {
    name: 'DisplayQuiz',
    props: ['houses'],
    data() {
      return {
        quizQuestions: [
          {
            topic: 'animal',
            text: "Which animal is the emblem of Gryffindor House?",
            correctHouse: 'gryffindor'
          },
          {
            topic: 'houseColours',
            text: "What color does Hufflepuff House wear?",
            correct: 'hufflepuff'
          },
          {
            topic: 'founder',
            text: "Which founder was head of Ravenclaw?",
            correct: 'ravenclaw'
          },
          {
            topic: 'ghost',
            text: "Which ghost belongs to Slytherin House?",
            correct: 'slytherin'
          },
        ]
      }
    },
    methods: {
      gradeQuiz() {
        alert('ur a wzrd hairy');
        // grade the quiz
      }
    }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
div input[type="radio"] {
  margin: 0 1em;
}
div label {
  display: inline-block;
  min-width: 160px;
  text-align: left;
}
a {
  color: #42b983;
}
</style>