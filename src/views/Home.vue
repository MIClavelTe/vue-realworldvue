<template>
  <div class="home">
    <h1>Flash Card App</h1>
    <ul>
      <li v-for="(card, index) in cards" :key="index">
        <Card :question="card.question" :answer="card.answer" />
      </li>
    </ul>
  </div>
</template>

<script>
import Card from "../components/card";
export default {
  components: {
    Card
  },
  data() {
    return {
      cards: [
        {
          question: "What's 1 + 1?",
          answer: "2"
        },
        {
          question: "What's 2 + 2?",
          answer: "4"
        },
        {
          question: "What's 3 + 3?",
          answer: "6"
        }
      ]
    };
  }
};
</script>
