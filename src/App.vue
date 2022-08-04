<template>
  <div id="app">
    <Cliente />
    <input v-model="codigoPai" type="text">
    <Produto :showQuantidade="false" :codigo="codigoPai" nome="Pendrive" quantidade="20" />
    <Produto :showQuantidade="true" codigo="AS5442" nome="CD" quantidade="2" />
  </div>
</template>

<script>
import Cliente from './components/Cliente'
import Produto from './components/Produto'

export default {
  name: 'App',
  data(){
    return {
      codigoPai: "55458"
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
