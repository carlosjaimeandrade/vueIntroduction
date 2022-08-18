<template>
  <div id="app">
    <Cliente />
    <input v-model="codigoPai" type="text">

    <hr>
        <h1>Cadastro de produtos</h1>
        <span v-show="erroNome">Você precisa preencher o nome</span> <br>
        <input :class="{'errorInput': erroNome}" v-model="nomeField" type="text" placeholder="nome"> <br>
        <input v-model="codigoField" type="text" placeholder="codigo"> <br>
        <button @click="cadastrandoProduto(obj)">Cadastrar</button>
    <hr>

   
    <div v-for="(produto, index) in orderProdutos" :key="produto.id">
      <p>{{index}}</p>
      <input v-model="produto.nome" type="text">
      <Produto @meDeleted="deletarUser" :tipo="true" :showQuantidade="true" :codigo="produto.codigo" :nome="produto.nome" quantidade="20" />
    </div>

  </div>
</template>

<script>
import _ from 'lodash';
import Cliente from './components/Cliente'
import Produto from './components/Produto'

export default {
  name: 'App',
  data() {
    return {
      erroNome: false,
      nomeField: "",
      codigoField: "",
      codigoPai: "55458",
      produtos: [
        {
          id: 1,
          nome: "Celular",
          codigo: "412"
        },
        {
          id: 2,
          nome: "x",
          codigo: "5"
        }
      ],
    }
  },
  components: {
    Cliente,
    Produto
  },
    methods: {
        cadastrandoProduto: function() {
            if(this.nomeField == ""){
              this.erroNome = true;
              setTimeout(()=>{
                this.erroNome = false;
              },5000)
              return
            }
            this.produtos.push({id: Date.now(), nome: this.nomeField, codigo: this.codigoField})
            console.log(this.produtos)
        },
        deletarUser: function (obj){
          console.log(`Deletando id ${obj.id}`)
          this.produtos = this.produtos.filter(produto =>{
            return produto.codigo != obj.id
          })
        }
    },
    computed:{
      orderProdutos: function (){
        return _.orderBy(this.produtos, ['id'], ['desc'])
      }
    }
}

</script>

<style>
  .errorInput{
    border: 1px solid red;
  }
</style>
