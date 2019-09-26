<template>
  <div>
    <h1>Flash Card App</h1>

    <Tabs />

    <router-view />
  </div>
</template>

<script>
import Tabs from "../components/tabs";
export default {
  components: {
    Tabs
  },
  data() {
    return {
      category: "",
      options: ["Addition", "Money"]
    };
  },
  computed: {
    whereTo() {
      return "/" + this.category;
    }
  }
};
</script>

<style>
.router {
  margin-bottom: 20px;
}
</style>
