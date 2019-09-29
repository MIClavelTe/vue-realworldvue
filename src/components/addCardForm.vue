<template>
  <form @submit.prevent="onSubmit">
    <p>
      <label>Question:</label>
      <input v-model="question" />
    </p>

    <p>
      <label>Answer:</label>
      <input v-model="answer" />
    </p>

    <p>
      <input type="submit" value="Submit" />
    </p>
  </form>
</template>

<script>
export default {
  data() {
    return {
      question: '',
      answer: ''
    }
  },
  methods: {
    onSubmit() {
      let card = {
        question: this.question,
        answer: this.answer
      }
      this.$emit('card-submitted', card)
      this.question = null
      this.answer = null
    }
  }
}
</script>

<style></style>
