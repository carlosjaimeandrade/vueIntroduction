<template>
    <div :class="{'admin': tipo, 'normal': !tipo}">
        <div>
            <h2>produto {{ codigo }}</h2>
            <p v-show="showQuantidade === true">Aqui é com o v-show</p>
            <p v-if="showQuantidade === true">Nome: {{ nome }}</p>
            <p v-else>Escondeu o nome</p>
            <p>Quantidade: {{ quantidade }}</p>
            <p>{{status}}</p>
            <button @click="mudarStatus($event)">{{status == true ? "desativar" : "ativar"}}</button>
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
        mudarStatus: function ($event){
            console.log($event.target.parentNode.children[0].innerHTML);
            this.status = !this.status
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