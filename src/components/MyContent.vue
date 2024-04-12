<script>
import DogsIndex from "./DogsIndex.vue";
export default {
  components: {
    DogsIndex,
  },
  data: function () {
    return {
      dogs: [
        { id: 1, name: "Teddy", age: 3, breed: "Golden retriever" },
        { id: 2, name: "Chloe", age: 6, breed: "Collie" },
      ],
    };
  },
};
</script>

<template>
  <main>
    <DogsIndex v-bind:dogs="dogs" />
  </main>
</template>

<style></style>
