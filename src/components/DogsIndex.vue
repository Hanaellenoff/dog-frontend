<script>
export default {
  props: {
    dogs: Array,
  },
};
</script>

<template>
  <div>
    <h1>All Dogs</h1>
    <div v-for="dog in dogs" v-bind:key="dog.id">
      <h2>{{ dog.name }}</h2>
      <p>{{ dog.age }}</p>
      <p>{{ dog.breed }}</p>
    </div>
  </div>
</template>

<style></style>
