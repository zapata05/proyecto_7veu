<script setup>
import {ref} from 'vue'
const name  = " soy una sobre escritura "
const stylecolor = "color: blue"
const arry=['blue','red','peru'];

const cambiar=ref['-','-','-','-','-','-','-','-','-'];

const camb =()=>{
  cambiar.value
}
</script>
<template>
<div class="container end">
  <h1 >hola<!--{{ name }}--></h1> 
  <h2 :style=stylecolor>pero azul</h2>
   
  <button 
  class="btn btn-primary" 
  data-bs-target="#collapseTarget" 
  data-bs-toggle="collapse">
  soy un boton
</button>
<div class="collapse py-2" id="collapseTarget">
  y yo un gato we
</div>
</div>
<div class="container1 bg-danger vh-400 p-2">
  <div class="row m-2 grid text-center ">
    <button class="col btn btn-primary btn-lg btn-block" @click="camb" ></button>
    <button class="col btn btn-primary btn-lg btn-block" @click="camb" ></button>
    <button class="col btn btn-primary btn-lg btn-block" @click="camb"></button>
  </div>
  <div class="row m-2 grid text-center">
    <button class="col btn btn-primary btn-lg btn-block" @click="camb" ></button>
    <button class="col btn btn-primary btn-lg btn-block" @click="camb" ></button>
    <button class="col btn btn-primary btn-lg btn-block" @click="camb"></button>
  </div>
  <div class="row m-2 grid text-center">
    <button class="col btn btn-primary btn-lg btn-block" @click="camb" ></button>
    <button class="col btn btn-primary btn-lg btn-block" @click="camb" ></button>
    <button class="col btn btn-primary btn-lg btn-block" @click="camb"></button>
  </div>
</div>
</template>

<style>  
h1{
  color: red;
}
</style>