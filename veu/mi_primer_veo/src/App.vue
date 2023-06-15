<template>
  
  <div class="game">
    <h1 >iniciar el juego perron del #</h1>
    <div class="scoreboard">
      <div class="player-score">
        Jugador X: {{ xScore }}
      </div>
      <div class="player-score">
        Jugador O: {{ oScore }}
      </div>
      <button @click="resetScores">Limpiar Marcador</button>
    </div>
    <div class="board">
      <div
        class="cell"
        v-for="(cell, index) in cells"
        :key="index"
        @click="handleCellClick(index)"
        :class="{ 'cell-selected': cell !== '' }"
      >
        {{ cell }}
      </div>
    </div>
    <div class="message" v-if="winner">
      ¡{{ winner }} ha ganado el juego!
    </div>
    <div class="button-container">
      <button @click="resetGame" :disabled="!winner">Reiniciar</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cells: Array(9).fill(""),
      currentPlayer: "X",
      winner: null,
      winningCombinations: [
        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],
        [0, 3, 6],
        [1, 4, 7],
        [2, 5, 8],
        [0, 4, 8],
        [2, 4, 6]
      ],
      xScore: 0,
      oScore: 0
    };
  },
  methods: {
    handleCellClick(index) {
      if (!this.cells[index] && !this.winner && !this.isBoardFull()) {
        this.cells[index] = this.currentPlayer;
        this.checkWinner();
        this.currentPlayer = this.currentPlayer === "X" ? "O" : "X";
      }
    },
    checkWinner() {
      for (let combination of this.winningCombinations) {
        const [a, b, c] = combination;
        if (
          this.cells[a] &&
          this.cells[a] === this.cells[b] &&
          this.cells[a] === this.cells[c]
        ) {
          this.winner = this.cells[a];
          this.updateScore();
          break;
        }
      }
      if (!this.winner && this.isBoardFull()) {
        this.winner = "Empate";
      }
    },
    updateScore() {
      if (this.winner === "X") {
        this.xScore++;
      } else if (this.winner === "O") {
        this.oScore++;
      }
    },
    isBoardFull() {
      return this.cells.every(cell => cell !== "");
    },
    resetGame() {
      this.cells = Array(9).fill("");
      this.currentPlayer = "X";
      this.winner = null;
    }
  },
  resetScores() {
      this.xScore = 0;
      this.oScore = 0;
    }
  
};
</script>

<style>
/* Estilos adicionales para el marcador */
.scoreboard {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin-bottom: 10px;
  font-size: 18px;
}

.player-score {
  margin-right: 20px;
}

/* Estilos previos mantenidos */
.game {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
}

.h1 {
  display: flex;
  align-items: center;
  align-content: center;
}

.board {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(3, 1fr);
  grid-gap: 10px;
  width: 300px;
  height: 300px;
  background-color: #fff;
  border: 1px solid #333;
  padding: 10px;
}

.cell {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #eee;
  border: 1px solid #ccc;
  font-size: 48px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.cell-selected {
  background-color: #d414148a;
  color: #fff;
}

.cell:hover:not(.cell-selected) {
  background-color: #ddd;
}

.cell.disabled {
  cursor: not-allowed;
  background-color: #ccc;
}

.button-container {
  margin-top: 20px;
}

button {
  padding: 10px 20px;
  font-size: 18px;
  background-color: #333;
  color: #fff;
  border: none;
  border: none;
  cursor: pointer;
}
.player-score {
  margin-right: 20px;
}
.message {
  margin-top: 20px;
  font-size: 24px;
}
</style>
