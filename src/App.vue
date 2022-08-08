<template>
  <div id="app">
    <Cliente />
    <input v-model="codigoPai" type="text">
    <Produto :tipo="true" :showQuantidade="false" :codigo="codigoPai" nome="Pendrive" quantidade="20" />
    <Produto :tipo="false" :showQuantidade="true" codigo="AS5442" nome="CD" quantidade="2" />

    <div v-for="(produto, index) in produtos" :key="produto.id">
      <p>{{index}}</p>
      <input v-model="produto.nome" type="text">
      <Produto :tipo="true" :showQuantidade="true" :codigo="produto.codigo" :nome="produto.nome" quantidade="20" />
    </div>

  </div>
</template>

<script>
import Cliente from './components/Cliente'
import Produto from './components/Produto'

export default {
  name: 'App',
  data() {
    return {
      codigoPai: "55458",
      produtos: [
        {
          id: 1,
          nome: "Celular",
          codigo: "44545"
        },
        {
          id: 2,
          nome: "Pendrive",
          codigo: "2323"
        }
      ],
    }
  },
  components: {
    Cliente,
    Produto
  }
}

</script>

<style>
</style>
