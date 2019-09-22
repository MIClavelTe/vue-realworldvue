<template>
  <div class="card">
    <button class="editButton" v-if="edit == false" @click="edit = true">
      Edit Flash Card
    </button>
    <button class="editButton" v-if="edit == true" @click="edit = false">
      Save
    </button>

    <h2>Question:</h2>
    <input
      class="editInput"
      type="text"
      v-if="edit == true"
      v-model="question"
    />

    <p v-if="edit == false">{{ question }}</p>

    <div v-if="edit == true">
      <h2>Answer:</h2>
      <input class="editInput" type="text" v-model="answer" />
    </div>

    <input
      type="text"
      placeholder="Your Answer"
      v-model="yourAnswer"
      v-if="edit == false"
    />
    <button @click="checkAnswer" v-if="edit == false">Submit</button>

    <h2 v-if="correct == true && edit == false">Correct!</h2>

    <div class="answerReveal" v-if="correct == false && edit == false">
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
      showAnswer: false,
      edit: false
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
  margin-left: 200px;
  margin-right: 200px;
  margin-bottom: 50px;
}

.answerReveal {
  margin-top: 10px;
  margin-bottom: 10px;
}

.editButton {
  margin-top: 10px;
}

.editInput {
  margin-bottom: 20px;
}
</style>
