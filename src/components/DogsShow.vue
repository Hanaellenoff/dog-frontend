<script>
export default {
    props: {
        photo: Object,
    },
};
</script>
<template>
    <div>
        <h1>Dog Info</h1>
        <p>Name: {{ dog.name }}</p>
        <p>Age: {{ dog.age }}</p>
        <p>Breed: {{ dog.breed }}</p>
    </div>
</template>

<style></style>