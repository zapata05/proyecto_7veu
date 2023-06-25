<script>
import App from '../App.vue';
import juego from './juego.vue'
App
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
    <juego></juego>
</template>