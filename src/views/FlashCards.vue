<template>
  <div>
    <h1>{{ $route.params.id }}</h1>

    <ol class="cards">
      <li v-for="(card, index) in cards" :key="index">
        <Card :question="card.question" :answer="card.answer" />
      </li>
    </ol>

    <!-- Only show remove div if more than 0 cards -->
    <div v-if="cards.length > 0">
      <p>Remove Flash Card #:</p>
      <input type="text" v-model="deletedCard" />
      <button @click="deleteCard">Delete</button>
    </div>

    <h2>Add Flash Card</h2>
    <AddCardForm @card-submitted="addCard" />
  </div>
</template>

<script>
import Card from '../components/card'
import AddCardForm from '../components/addCardForm'
export default {
  props: {
    cards: {
      type: Array,
      required: true
    }
  },
  components: {
    Card,
    AddCardForm
  },
  data() {
    return {
      deletedCard: 1
    }
  },
  methods: {
    deleteCard() {
      var start = this.deletedCard - 1
      this.cards.splice(start, 1)
    },
    addCard(card) {
      this.cards.push(card)
    }
  }
}
</script>
