<template>
  <h1>Let's guess Head or Tail</h1>
  <Coin :isPlaying="isPlaying" :result="result" />
  <button class="play-btn" @click="startGame" v-if="isPlaying === false">
    Play
  </button>
  <Guess v-if="isPlaying" />
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
    };
  },

  methods: {
    startGame() {
      this.isPlaying = true;
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
