<script>
import App from '../App.vue';


</script>
<template>
<app></app>
    <div class="container text-center " style=" background-color: royalblue; display:flexbox;">
      <div id="pepe" class="text-center " style="background-color: cornsilk; align-items:center;">
  <div class="d-flex justify-content-flex-start align-content-center"  style="margin-block-end: 20px;">
  <button id="Button1" :class="array[0] != '-'? 'btn btn-success disabled':'btn btn-dark'  " style="height: 100px; width: 100px; margin-right: 20px; " @click="cambiar(0)" >{{ array[0] }}</button>
  <button id="Button2" :class="array[1] != '-'? 'btn btn-success disabled':'btn btn-dark'"  style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(1)">{{ array[1] }}</button>
  <button id="Button3" :class="array[2] != '-'? 'btn btn-success disabled':'btn btn-dark'" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(2)">{{ array[2] }}</button>
  </div>
  <div class="d-flex justify-content-flex-start aline-content-center" style="margin-block-end: 20px;">
  <button id="Button4" :class="array[3] != '-'? 'btn btn-success disabled':'btn btn-dark'" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(3)" >{{ array[3] }}</button>
  <button id="Button5" :class="array[4] != '-'? 'btn btn-success disabled':'btn btn-dark'" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(4)">{{ array[4] }}</button>
  <button id="Button6" :class="array[5] != '-'? 'btn btn-success disabled':'btn btn-dark'" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(5)">{{ array[5] }}</button>
  </div>
  <div class="d-flex justify-content-flex-start aline-content-center" style="margin-block-end: 20px;">
  <button id="Button7" :class="array[6] != '-'? 'btn btn-success disabled':'btn btn-dark'" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(6)">{{ array[6] }}</button>
  <button id="Button8" :class="array[7] != '-'? 'btn btn-success disabled':'btn btn-dark'" style="height: 100px; width: 100px; margin-right: 20px; " @click="cambiar(7)">{{ array[7] }}</button>
  <button id="Button9" :class="array[8] != '-'? 'btn btn-success disabled':'btn btn-dark'" style="height: 100px; width: 100px; margin-right: 20px; " @click="cambiar(8)">{{ array[8] }}</button>
  </div>
  </div>
  <br>
  <br>
  <button id="reiniciar" class="btn btn-primary" @click="reiniciar()">Reiniciar </button>
  
  </div>
  <div class="container2 felx text-center" style=" background-color: rebeccapurple; display:flexbox;">
<div style="height: 25px; font-size:xx-large;" v-show="msge">  el ganador es {{turno}} 
  </div>
  <br>
  <br>
  <h1>#departidas{{partidas  }}</h1>
  <h1>gano {{jug1}} x: {{px  }}</h1>
  <h1>gano {{jug2}} o: {{po }}</h1>
 <div> <button id="reiniciarm" class="btn btn-primary" @click="reiniciarmarc()">Reiniciar el marcador</button></div>
 <div>
  <h2>escribe jugador 1</h2>
  <input type="text" v-model.leyzi="jug1">
  <h2>escribe jugador 2</h2>
  <input type="text" v-model.leyzi="jug2">
  <br>   
  <br>
  <button id="reiniciar" @click="cambiarnom">agrega</button>
 </div>
</div>  
  </template>