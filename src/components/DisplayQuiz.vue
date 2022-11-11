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
import { text } from 'body-parser';


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
            correctHouse: 'hufflepuff'
          },
          {
            topic: 'founder',
            text: "Which founder was head of Ravenclaw?",
            correctHouse: 'ravenclaw'
          },
          {
            topic: 'ghost',
            text: "Which ghost belongs to Slytherin House?",
            correctHouse: 'slytherin'
          },
          {
            topic: 'element',
            text: "Which element represents Hufflepuff?",
            correctHouse: 'hufflepuff'
          },
        ]
      }
    },
    methods: {
      gradeQuiz() {
      alert('yer a wzrd hairy');
        // grade the quiz
        // var score = 0;

        // for(var i=0; i < text.length; i++)
        // var response = text(text[i.text])
        // if(response == text[i].correctHouse){
        // this.score++;
        // } else {
        //   score = null;
        // }
        // alert("you got " + score + "/" + text.length);
    }
      },
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