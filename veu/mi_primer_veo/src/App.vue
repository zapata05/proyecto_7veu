
<script setup>
import { computed, ref } from 'vue';
import juego from './components/juego.vue';
import marcador from './components/marcador.vue';


</script>
<template>
  
<juego></juego>
<marcador></marcador>
 
</template>
<style>
#pepe{
  display:grid;
 align-self: center;
  align-items: center;
  align-content: center;
}
.container {
  padding: 15%;
  height: 100%;
  width: 100%;
  align-items: center;
  display: flex;
  flex-direction: column;
  justify-content: center;

}
.container2{
  padding: 10%;
  height: 100%;
  width: 100%;
  align-items: center;
  display: flex;
  flex-direction: column;
  justify-content: center;

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
  font-size: 1px;
  margin-bottom: 8px;
}
</style>