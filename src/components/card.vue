<template>
  <div class="card">
    <h2>Question:</h2>
    <p>{{ question }}</p>

    <input type="text" placeholder="Your Answer" v-model="yourAnswer" />
    <button @click="checkAnswer">Submit</button>

    <h2 v-if="correct == true">Correct!</h2>

    <div class="answerReveal" v-if="correct == false">
      <button @click="revealAnswer">Reveal Answer</button>
      <h3 v-if="showAnswer == true">{{ answer }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    question: {
      type: String,
      required: true
    },
    answer: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      yourAnswer: "",
      correct: false,
      showAnswer: false
    };
  },
  methods: {
    checkAnswer() {
      if (this.yourAnswer == this.answer) {
        return (this.correct = true);
      }
    },
    revealAnswer() {
      return (this.showAnswer = true);
    }
  }
};
</script>

<style>
.card {
  border: 2px black dotted;
  margin-left: 500px;
  margin-right: 500px;
  margin-bottom: 50px;
}

.answerReveal {
  margin-top: 10px;
  margin-bottom: 10px;
}
</style>
