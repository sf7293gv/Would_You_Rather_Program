<template>
  <div id="app">

    <h1>Would you rather...</h1>

    <would-you-rather
        v-bind:questions="questions"
        v-on:answer-changed="answerChanged"
        v-on:answer-changed2="answerChanged2"
        v-on:answer-changed3="answerChanged3">

    </would-you-rather>

    <ul class="ulist">
        <li v-for="choice in choices">{{ choice }}</li>
    </ul>


  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      questions: [
        {
          id: 0,
          wyrQuestion: 'Would you rather pick color green or blue?',
          wyrAnswer1: 'Green',
          wyrAnswer2: 'Blue',
        },
        {
          id: 1,
          wyrQuestion: 'Would you rather pick color pink or purple?',
          wyrAnswer1: 'Pink',
          wyrAnswer2: 'Purple',
        },
        {
          id: 2,
          wyrQuestion: 'Would you rather pick color yellow or red?',
          wyrAnswer1: 'Yellow',
          wyrAnswer2: 'Red',
        }
      ],
      choices: []
    }
  },
  methods: {
    answerChanged(choice, choice2, choice3) {
      console.log(choice)
      this.choices = [choice, choice2, choice3]
      this.userSelection = `You chose ${choice}`
    },
    // answerChanged2(choice2) {
    //   console.log(choice2)
    //   this.userSelection2 = `You chose ${choice2}`
    // },
    // answerChanged3(choice3) {
    //   console.log(choice3)
    //   this.userSelection3 = `You chose ${choice3}`
    // }
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

.ulist {
  background-color: aqua;
}
</style>
