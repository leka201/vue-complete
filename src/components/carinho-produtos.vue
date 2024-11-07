<script setup>

import { ref } from "vue";

let contador = ref(0);
let produtos = ref("Nada");

function add_produto(){
    contador.value++
}

function alerta(){
    alert("Compra finalizada com sucesso");
}

function muda_chocolate(){
    produtos.value = "Chocolates";
}
function muda_quintandas(){
    produtos.value = "Quintandas";
}

function oculta_produto(){
    produtos.value = "Nada"
}

//exemplo de como fz td isso numa função só

//function muda_categoria(valor){categoria.value = valor;}

</script>


<template>

    <h1><strong>Seu carinho:</strong></h1>
    <p>Produtos adcionados: <strong>{{ contador }}</strong></p>
    <button v-on:click="alerta()">Finalizar Compra</button>
    <hr/>
    <p>Selecione a categoria que deseja ver:</p>
    
        <li v-on:click="muda_chocolate()">Chocolates de Chokito</li>
        <li v-on:click="muda_quintandas()">Quintadas de Chokito</li>
        <li v-on:click="oculta_produto()">Ocultar produtos</li>
    

    <h2><strong>Chocolates de Chokito</strong></h2>

    <div v-if="produtos == 'Chocolates'">   
        <li>Chokito Tradicional <button v-on:click="add_produto()">Adicionar</button></li>
        <li>Chokito Branco <button v-on:click="add_produto()">Adicionar</button></li>
        <li>Chokito Chocolate Amargo <button v-on:click="add_produto()">Adicionar</button></li>
    </div>

    <div v-if="produtos == 'Quintandas'">   
        <li>Bolo de Chokito <button v-on:click="add_produto()">Adicionar</button></li>
        <li>Bombom de Chookito <button v-on:click="add_produto()">Adicionar</button></li>
    </div>


</template>