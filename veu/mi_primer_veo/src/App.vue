<script setup>
const name  = " soy una sobre escritura "
const stylecolor = "color: blue"
const arry=['blue','red','peru'];
</script>
<template>
<div class="container">
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
</template>

<style>
h1{
  color: red;
}
</style>