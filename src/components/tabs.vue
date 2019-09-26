<template>
  <div>
    <p
      class="tab"
      :class="{ activeTab: selectedTab === tab }"
      v-for="(tab, index) in tabs"
      :key="index"
      @click="selectedTab = tab"
    >
      {{ tab }}
    </p>

    <FlashCards :cards="additionCards" v-show="selectedTab === 'Addition'" />

    <FlashCards :cards="moneyCards" v-show="selectedTab === 'Money'" />
  </div>
</template>

<script>
import FlashCards from "../views/FlashCards";
export default {
  components: {
    FlashCards
  },
  data() {
    return {
      tabs: ["Addition", "Money"],
      selectedTab: "Addition",
      additionCards: [
        {
          question: "What's 1 + 1?",
          answer: "2"
        }
      ],
      moneyCards: [
        {
          question: "What's 1 dime?",
          answer: "10"
        }
      ]
    };
  }
};
</script>

<style>
.activeTab {
  color: rgb(48, 182, 115);
  text-decoration: rgb(48, 182, 115) underline;
  font-weight: bold;
}
</style>
