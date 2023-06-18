
<script setup>
import { ref } from 'vue';
let array=ref(["-","-","-","-","-","-","-","-","-"])
let turno= ref("X")
let msge=ref(false)
let partidas= ref(0)
let px= ref(0)
let po= ref(0)
function reiniciarmarc(){
po.value=0;
px.value=0;
partidas.value=0;
}
var valoresActuales = [];
function reiniciar() {
    // Guardar los valores actuales en el arreglo
    valoresActuales.push(array.value[0]);
    valoresActuales.push(array.value[1]);
    valoresActuales.push(array.value[2]);
    valoresActuales.push(array.value[3]);
    valoresActuales.push(array.value[4]);
    valoresActuales.push(array.value[5]);
    valoresActuales.push(array.value[6]);
    valoresActuales.push(array.value[7]);
    valoresActuales.push(array.value[8]);

    // Reiniciar los valores a sus valores iniciales
    array.value[0] ="-";
    array.value[1]="-";
    array.value[2]="-";
    array.value[3] ="-";
    array.value[4]="-";
    array.value[5]="-";
    array.value[6] ="-";
    array.value[7]="-";
    array.value[8]="-";

    document.getElementById("Button1").disabled = false;
    document.getElementById("Button2").disabled = false;
    document.getElementById("Button3").disabled = false;
    document.getElementById("Button4").disabled = false;
    document.getElementById("Button5").disabled = false;
    document.getElementById("Button6").disabled = false;
    document.getElementById("Button7").disabled = false;
    document.getElementById("Button8").disabled = false;
    document.getElementById("Button9").disabled = false;

    msge.value=false
  }
const cambiar=(i)=>{
  if (turno.value =="X")
   {
    array.value[i]="X"
    turno.value ="O"
  }
  else {
    array.value[i] ="O"
    turno.value="X" 
  }
ganador()
bloquear()
  }

  const ganador=()=>{
    if(array.value[0] == array.value[1] && array.value[1] == array.value[2] && array.value[0] !== "-" && array.value[1] !=="-" && array.value[2] !== "-")
  {
    msge.value=true
    turno.value=array.value[0]
    partidas.value++
    if(array.value[0]=="X")
    px.value++
    else
    po.value++
  }
  if(array.value[3] == array.value[4] && array.value[4] == array.value[5] && array.value[3] !== "-" && array.value[4] !=="-" && array.value[5] !== "-")
  {
    msge.value=true
    turno.value=array.value[3]
    partidas.value++
    if(array.value[3]=="X")
    px.value++
    else
    po.value++
  }
  if(array.value[6] == array.value[7] && array.value[7] == array.value[8] && array.value[6] !== "-" && array.value[7] !=="-" && array.value[8] !== "-")
  {
    msge.value=true
    turno.value=array.value[6]
    partidas.value++
    if(array.value[6]=="X")
    px.value++
    else
    po.value++
  }
  if(array.value[0] == array.value[3] && array.value[3] == array.value[6] && array.value[0] !== "-" && array.value[3] !=="-" && array.value[6] !== "-")
  {
    msge.value=true
    turno.value=array.value[0]
    partidas.value++
    if(array.value[0]=="X")
    px.value++
    else
    po.value++
  }
  if(array.value[1] == array.value[4] && array.value[4] == array.value[7] && array.value[1] !== "-" && array.value[4] !=="-" && array.value[7] !== "-")
  {
    msge.value=true
    turno.value=array.value[1]
    partidas.value++
    if(array.value[1]=="X")
    px.value++
    else
    po.value++
  }
  if(array.value[2] == array.value[5] && array.value[5] == array.value[8] && array.value[2] !== "-" && array.value[5] !=="-" && array.value[8] !== "-")
  {
    msge.value=true
    turno.value=array.value[2]
    partidas.value++
    if(array.value[2]=="X")
    px.value++
    else
    po.value++
  }
  if(array.value[0] == array.value[4] && array.value[4] == array.value[8] && array.value[0] !== "-" && array.value[4] !=="-" && array.value[8] !== "-")
  {
    msge.value=true
    turno.value=array.value[0]
    partidas.value++
    if(array.value[0]=="X")
    px.value++
    else
    po.value++
  }
  if(array.value[2] == array.value[4] && array.value[4] == array.value[6] && array.value[2] !== "-" && array.value[4] !=="-" && array.value[6] !== "-")
  {
    msge.value=true
    turno.value=array.value[2]
    partidas.value++
    if(array.value[2]=="X")
    px.value++
    else
    po.value++
  }
  }

  const bloquear=()=>{
    if (msge.value==true) {
    document.getElementById("Button1").disabled = true;
    document.getElementById("Button2").disabled = true;
    document.getElementById("Button3").disabled = true;
    document.getElementById("Button4").disabled = true;
    document.getElementById("Button5").disabled = true;
    document.getElementById("Button6").disabled = true;
    document.getElementById("Button7").disabled = true;
    document.getElementById("Button8").disabled = true;
    document.getElementById("Button9").disabled = true;
  } 

  }
  

</script>
<template>
  
  <div class="container text-center " style=" background-color: royalblue; display:flexbox;">
    <div id="pepe" class="text-center" style="background-color: cornsilk; align-self:center">
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

<div class="container2 text-center" style=" background-color: rebeccapurple; display:flexbox;">
<div style="height: 25px; font-size:xx-large;" v-show="msge">  el ganador es {{turno}} 
  </div>
  <br>
  <br>
  <h1>  numero de partidas {{partidas  }}</h1>
  <h1> puntos de x {{px  }}</h1>
  <h1>  puntos de o {{po }}</h1>
  <button id="reiniciarm" class="btn btn-primary" @click="reiniciarmarc()">Reiniciar el marcador</button>
    </div>

</template>
<style>
#pepe{
  display:grid;
 align-self: center;
  align-items: center;
  align-content: center;
}
.container {
  background-color: khaki;
  align-items: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 20px;
}

.board {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 20px;
  
}
#reiniciar{
  padding: 10px 20px;
  font-size: 18px;
  background-color: #333;
  color: #fff;
  border: none;
  border: none;
  cursor: pointer;
}
#reiniciarm{
  padding: 10px 20px;
  font-size: 18px;
  background-color: #333;
  color: #fff;
  border: none;
  border: none;
  cursor: pointer;
}

.cell {
  height: 100px;
  width: 100px;
  margin-right: 20px;
  font-size: 24px;
}

.button-container {
  margin-top: 20px;
}

.button-container button {
  margin-right: 10px;
}

.message {
  height: 25px;
  font-size: 28px;
  font-weight: bold;
}

h1 {
  font-size: 24px;
  margin-bottom: 10px;
}
</style>