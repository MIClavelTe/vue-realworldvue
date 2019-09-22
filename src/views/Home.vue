<template>
  <div>
    <h1>Flash Card App</h1>

    <h3>Find Category</h3>
    <p>
      <select v-model="category">
        <option>Addition</option>
        <option>Money</option>
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
      category: ""
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
