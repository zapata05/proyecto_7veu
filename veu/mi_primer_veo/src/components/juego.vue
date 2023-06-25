<template>
  <div class="container text-center" style="background-color: royalblue; display:flexbox;">
    <div id="pepe" class="text-center" style="background-color: cornsilk; align-items:center;">
      <div class="d-flex justify-content-flex-start align-content-center" style="margin-block-end: 20px;">
        <button id="Button1" :class="getButtonClass(0)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(0)">{{ array[0] }}</button>
        <button id="Button2" :class="getButtonClass(1)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(1)">{{ array[1] }}</button>
        <button id="Button3" :class="getButtonClass(2)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(2)">{{ array[2] }}</button>
      </div>
      <div class="d-flex justify-content-flex-start aline-content-center" style="margin-block-end: 20px;">
        <button id="Button4" :class="getButtonClass(3)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(3)">{{ array[3] }}</button>
        <button id="Button5" :class="getButtonClass(4)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(4)">{{ array[4] }}</button>
        <button id="Button6" :class="getButtonClass(5)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(5)">{{ array[5] }}</button>
      </div>
      <div class="d-flex justify-content-flex-start aline-content-center" style="margin-block-end: 20px;">
        <button id="Button7" :class="getButtonClass(6)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(6)">{{ array[6] }}</button>
        <button id="Button8" :class="getButtonClass(7)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(7)">{{ array[7] }}</button>
        <button id="Button9" :class="getButtonClass(8)" style="height: 100px; width: 100px; margin-right: 20px;" @click="cambiar(8)">{{ array[8] }}</button>
      </div>
    </div>
    <br>
    <br>
    <button id="reiniciar" class="btn btn-primary" @click="reiniciar()">Reiniciar</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      array: ["-", "-", "-", "-", "-", "-", "-", "-", "-"],
      turno: "X",
      msge: false,
    };
  },
  methods: {
    cambiar(i) {
      if (this.turno === "X") {
        this.array[i] = "X";
        this.turno = "O";
      } else {
        this.array[i] = "O";
        this.turno = "X";
      }
      this.ganador();
      this.bloquear();
    },
    ganador() {
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
    },
    bloquear() {
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

    },
    reiniciar() {
    
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
    },
    getButtonClass(index) {
      return this.array[index] !== "-" ? "btn btn-success disabled" : "btn btn-dark";
    },
  },
};
</script>