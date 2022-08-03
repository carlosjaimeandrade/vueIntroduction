<template>
  <div id="app">
    <h1>Ola </h1>
    <Cliente />
    <Cliente />
    <Cliente />
    <Produto />
    <Produto />
    <Produto />
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
