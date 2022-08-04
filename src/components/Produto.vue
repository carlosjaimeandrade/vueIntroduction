<template>
    <div>
        <div>
            <h2>produto {{ codigo }}</h2>
            <p>Nome: {{ nome }}</p>
            <p>Quantidade: {{ quantidade }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        nome: String,
        quantidade: Number,
        codigo: String
    }
}
</script>

<style>
</style>