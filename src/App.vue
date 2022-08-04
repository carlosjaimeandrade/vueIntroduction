<template>
  <div id="app">
    <Cliente />
    <Produto codigo="AS5441" nome="Pendrive" quantidade="20" />
    <Produto codigo="AS5442" nome="CD" quantidade="2" />
  </div>
</template>

<script>
import Cliente from './components/Cliente'
import Produto from './components/Produto'

export default {
  name: 'App',
  components: {
    Cliente,
    Produto
  }
}

</script>

<style>
</style>
