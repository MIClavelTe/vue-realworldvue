<template>
  <div>
    <h1>Flash Card App</h1>

    <h3>Find Category</h3>
    <p>
      <select v-model="category">
        <option v-for="(option, index) in options" :key="index">
          {{ option }}
        </option>
      </select>
    </p>

    <router-link :to="whereTo">{{ category }}</router-link>

    <router-view />
  </div>
</template>

<script>
export default {
  data() {
    return {
      category: "",
      options: ["Addition", "Subtraction"]
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
