<template>
    <div>
        <h1>{{ email }}</h1>
        <p>Cliente {{ nome }}</p>
        <p>idade {{ idade }}</p>
        <input :value="nome" type="text">
        <input v-model="nome" type="text">
        <hr>
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