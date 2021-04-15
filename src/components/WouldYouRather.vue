<template>
  <div class="wyr">

    <h2>Please make your choice</h2>
    <div class="q">

    <h3>{{ questions[0].wyrQuestion }}</h3>

    <input type="radio" v-model="choice" v-bind:value="questions[0].wyrAnswer1" v-on:change="choiceMade">
    <label>{{ questions[0].wyrAnswer1 }}</label>

    <input type="radio" v-model="choice" v-bind:value="questions[0].wyrAnswer2" v-on:change="choiceMade">
    <label>{{ questions[0].wyrAnswer2 }}</label>

    </div>

    <div class="q">

      <h3>{{ questions[1].wyrQuestion }}</h3>

      <input type="radio" v-model="choice2" v-bind:value="questions[1].wyrAnswer1" v-on:change="choiceMade">
      <label>{{ questions[1].wyrAnswer1 }}</label>

      <input type="radio" v-model="choice2" v-bind:value="questions[1].wyrAnswer2" v-on:change="choiceMade">
      <label>{{ questions[1].wyrAnswer2 }}</label>

    </div>

    <div class="q">

      <h3>{{ questions[2].wyrQuestion }}</h3>

      <input type="radio" v-model="choice3" v-bind:value="questions[2].wyrAnswer1" v-on:change="choiceMade">
      <label>{{ questions[2].wyrAnswer1 }}</label>

      <input type="radio" v-model="choice3" v-bind:value="questions[2].wyrAnswer2" v-on:change="choiceMade">
      <label>{{ questions[2].wyrAnswer2 }}</label>

    </div>

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    questions: [],
  },
  data() {
    return {
      choice: '',
      choice2: '',
      choice3: ''
    }
  },
  methods: {
    choiceMade() {
      this.$emit('answer-changed', this.choice, this. choice2, this.choice3)
    }
    // choiceMade2() {
    //   this.$emit('answer-changed2', this.choice2)
    // },
    // choiceMade3() {
    //   this.$emit('answer-changed3', this.choice3)
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

.wyr {
  border: 2px black solid;
  background: aquamarine;
}

.q {
  margin: 20px 0 0;
  border: 1px black solid;
  background-color: cadetblue;
}

</style>
