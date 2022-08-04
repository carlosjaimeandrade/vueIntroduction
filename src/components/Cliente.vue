<template>
    <div>

        <h1>{{ email }}</h1>
        <h2>Cliente {{ nome }} idade {{ idade }}</h2>

        <input :value="nome" type="text">
        <hr>
        <input v-model="nome" type="text">
    </div>
</template>

<script>
export default {
    data() {
        return {
            nome: "Carlos",
            idade: 25,
            email: "jaime_andrek@hotmail.com"
        }
    }
}
</script>

<style scoped>
.client {
    background-color: rgba(92, 83, 83, 0.24);
}
</style>