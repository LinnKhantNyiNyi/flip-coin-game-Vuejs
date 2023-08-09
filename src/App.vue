<template>
  <h2>Let's guess Head or Tail</h2>
  <Coin :isPlaying="isPlaying" :result="result" />
  <button class="play-btn" @click="startGame" v-if="isPlaying === false">
    Play
  </button>
  <p>{{ message }}</p>
  <p v-if="Win">
    You win. It's <span v-if="result == 'H'">Head</span
    ><span v-if="result == 'T'">Tail</span>
  </p>
  <p v-if="Win == false">
    You lose It's <span v-if="result == 'H'">Head</span
    ><span v-if="result == 'T'">Tail</span>
  </p>
  <Guess v-if="isPlaying" @guess="guess" />
</template>

<script>
import Coin from "./components/coin.vue";
import Guess from "./components/guess.vue";
export default {
  name: "App",

  components: {
    Coin,
    Guess,
  },

  data() {
    return {
      isPlaying: false,
      result: "",
      Win: null,
      message: "",
    };
  },

  methods: {
    startGame() {
      this.isPlaying = true;
      this.result = "";
      this.Win = null;
    },

    guess(guessedSide) {
      this.message = "Wait for it..";
      setTimeout(() => {
        this.CheckWinLose(guessedSide);
      }, 6000);
    },

    CheckWinLose(guessedSide) {
      let x = Math.random() * 2 + 1;
      let y = Math.floor(x);
      if (y === guessedSide) {
        this.Win = true;
      } else {
        this.Win = false;
      }
      if (y === 1) {
        this.result = "H";
      } else {
        this.result = "T";
      }
      this.isPlaying = false;
      this.message = "";
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.play-btn {
  padding: 20px 40px;
  border-radius: 5px;
  border: 0;
  cursor: pointer;
  background-color: rgb(105, 194, 105);
  color: white;
  font-size: 20px;
}
</style>
