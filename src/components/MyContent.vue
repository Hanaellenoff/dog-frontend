<script>
import DogsIndex from "./DogsIndex.vue";
import MyModal from "./MyModal.vue";
import DogsShow from "./DogsShow.vue";
import axios from "axios";

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

    handleUpdateDog: function (id, params) {
      console.log("handleUpdateDog", id, params);
      axios.patch(`http://127.0.0.1:5000/dogs/${id}.json`, params).then((response) => {
        console.log("dogs update", response);
        this.dogs = this.dogs.map((dog) => {
          if (dog.id === response.data.id) {
            return response.data;
          } else {
            return dog;
          }
        });
        this.handleClose();
      })
      .catch((error) => {
        console.log("dogs update error", error.response);
      });
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
        <DogsShow v-bind:dog="currentDog" v-on:updateDog="handleUpdateDog" />
    </MyModal>
  </main>
</template>

<style></style>
