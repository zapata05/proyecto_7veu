<template>
    <div class="container2 felx text-center" style="background-color: rebeccapurple; display:flexbox;">
      <div style="height: 25px; font-size:xx-large;" v-show="msge">
        El ganador es {{ turno }}
      </div>
      <br>
      <br>
      <h1>#departidas{{ partidas }}</h1>
      <h1>Gano {{ jug1 }} x: {{ px }}</h1>
      <h1>Gano {{ jug2 }} o: {{ po }}</h1>
      <div>
        <button id="reiniciarm" class="btn btn-primary" @click="reiniciarmarc()">Reiniciar el marcador</button>
      </div>
      <div>
        <h2>Escribe jugador 1</h2>
        <input type="text" v-model.lazy="jug1">
        <h2>Escribe jugador 2</h2>
        <input type="text" v-model.lazy="jug2">
        <br>   
        <br>
       
      </div>
    </div>
    <juego></juego>
  </template>
  
  <script>
  import juego from './juego.vue';
  export default {
    data() {
      return {
        msge: false,
        partidas: 0,
        px: 0,
        po: 0,
        jug1: "jugador1",
        jug2: "jugador2",
      };
    },
    methods: {
      reiniciarmarc() {
        this.po = 0;
        this.px = 0;
        this.partidas = 0;
        this.jug1 = "jugador1";
        this.jug2 = "jugador2";
      },
      cambiarnom() {
        // Logic for changing player names
        // ...
      },
    },
  };
  </script>
