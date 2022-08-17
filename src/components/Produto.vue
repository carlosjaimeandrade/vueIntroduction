<template>
    <div :class="{'admin': tipo, 'normal': !tipo}">
        <div>
            <h2>produto {{ codigo }}</h2>
            <p v-show="showQuantidade === true">Aqui é com o v-show</p>
            <p v-if="showQuantidade === true">Nome: {{ processarNome }}</p>
            <p v-else>Escondeu o nome</p>
            <p>Quantidade: {{ quantidade }}</p>
            <p></p>
            <button @click="mudarStatus($event)">{{status == true ? "desativar" : "ativar"}}</button>
            <button  :id="codigo" @click="emitirEventos($event)">Deletar</button>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            status: true
        }
    },
    props: {
        nome: String,
        quantidade: Number,
        codigo: String,
        showQuantidade: Boolean,
        tipo: Boolean
    },
    methods: {
        emitirEventos: function ($event) {
            this.$emit('meDeleted',{id: $event.target.id, component: this});
        }
    },
    computed:{
        processarNome: function(){
            return this.nome.toUpperCase();
        }
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