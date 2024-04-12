<script>
export default {
    props: {
        photo: Object,
    },
    data: function () {
        return {
            editDogParams: {},
        };
    },
    created: function () {
        this.editDogParams = { ...this.dog};
    },
    methods: {
        handleSubmit: function () {
            this.$emit("updateDog", this.dog.id, this.editDogParams);
        },
    },
};
</script>
<template>
    <div>
        <h1>Dog Info</h1>
        <p>Name: {{ dog.name }}</p>
        <p>Age: {{ dog.age }}</p>
        <p>Breed: {{ dog.breed }}</p>
        <form v-on:submit.prevent="handleSubmit">
            <div>
                Name:
                <input v-model="editDogParams.name" type="text">
            </div>
            <div>
                Age:
                <input v-model="editDogParams.age" type="text">
            </div>
            <div>
                Breed:
                <input v-model="editDogParams.breed" type="text">
            </div>
            <button type="submit">Update Dog</button>
        </form>
    </div>
</template>

<style></style>