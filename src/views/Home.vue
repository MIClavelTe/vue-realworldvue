<template>
  <div class="home">
    <h1>Flash Card App</h1>
    <ol>
      <li v-for="(card, index) in cards" :key="index">
        <Card :question="card.question" :answer="card.answer" />
      </li>
    </ol>

    <p>Remove Flash Card #:</p>
    <input type="text" v-model="deletedCard" />
    <button @click="deleteCard">Delete</button>
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
      ],
      deletedCard: 1
    };
  },
  methods: {
    deleteCard() {
      var start = this.deletedCard - 1;
      this.cards.splice(start, 1);
    }
  }
};
</script>
