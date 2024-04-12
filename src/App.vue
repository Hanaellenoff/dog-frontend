<script>
import MyHeader from "./components/MyHeader.vue";
import MyContent from "./components/MyContent.vue";
import MyFooter from "./components/MyFooter.vue";

export default {
  name: "app",
  components: {
    MyHeader,
    MyContent,
    MyFooter,
  },
};
</script>

<template>
  <div>
    <MyHeader />
    <MyContent />
    <MyFooter />
  </div>
</template>

<style scoped></style>
