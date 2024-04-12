<script>
import DogsIndex from "./DogsIndex.vue";
import MyModal from "./MyModal.vue";
import DogsShow from "./DogsShow.vue";

export default {
  components: {
    DogsIndex,
    MyModal,
    DogsShow,
},
data: function () {
    return {
      dogs: [
        { id: 1, name: "Teddy", age: 3, breed: "Golden retriever" },
        { id: 2, name: "Chloe", age: 6, breed: "Collie" },
      ],
      currentDog: {},
      isDogsShowVisible: false,
    };
},
    handleShowDog: function (dog) {
        console.log("handleShowDog", dog);
        this.currentDog = dog;
        this.isDogsShowVisible = true;
    },
    handleClose: function () {
        this.isDogsShowVisible = false;
    },
};
</script>

<template>
  <main>
    <DogsIndex v-bind:dogs="dogs" v-on:showDog="handleShowDog" />
    <MyModal v-bind:show="isDogsShowVisible" v-on:close="handleClose">
        <DogsShow v-bind:dog="currentDog" />
    </MyModal>
  </main>
</template>

<style></style>
