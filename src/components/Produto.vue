<template>
    <div :class="{'admin': tipo, 'normal': !tipo}">
        <div>
            <h2>produto {{ codigo }}</h2>
            <p v-show="showQuantidade === true">Aqui é com o v-show</p>
            <p v-if="showQuantidade === true">Nome: {{ nome }}</p>
            <p v-else>Escondeu o nome</p>
            <p>Quantidade: {{ quantidade }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        nome: String,
        quantidade: Number,
        codigo: String,
        showQuantidade: Boolean,
        tipo: Boolean
    }
}
</script>

<style>
.admin{
    background-color: red;
}
.normal{
    background-color: aqua;
}
</style>