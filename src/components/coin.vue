<template>
  <div class="coin" :class="{ coinanimation: isPlaying }">
    <div class="head" :class="{ headanimation: isPlaying }">
      <img
        v-if="isPlaying"
        src="../assets/imgs/head.png"
        alt=""
        class="headside"
      />

      <img
        v-if="result == 'H'"
        src="../assets/imgs/head.png"
        alt=""
        class="headside"
      />

      <img
        v-if="result == 'T'"
        src="../assets/imgs/tail.png"
        alt=""
        class="tailside"
      />
    </div>
    <div v-if="isPlaying" :class="{ tailanimation: isPlaying }" class="tail">
      <img
        v-if="isPlaying"
        src="../assets/imgs/tail.png"
        alt=""
        class="tailside"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: ["isPlaying", "result"],
};
</script>

<style>
.coin {
  width: 200px;
  height: 200px;
  background-color: rgb(224, 201, 68);
  text-align: center;
  border: 5px solid black;
  border-radius: 50%;
  margin: 100px auto;
  margin-bottom: 50px;
  position: relative;
  /* animation: flip 0.7s infinite; */
  perspective: 1000px;
}

.head,
.tail {
  position: absolute;
  top: 10px;
  left: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid black;
  width: 180px;
  height: 180px;
  border-radius: 50%;
  font-size: 30px;
}

.coinanimation {
  animation: flip 0.7s infinite;
}
.headanimation {
  animation: flip-text-head 0.7s infinite;
}
.tailanimation {
  animation: flip-text-tail 0.7s infinite;
}

.headside {
  position: relative;
  top: -20px;
  width: 380px;
  border-radius: 50%;
}
.tailside {
  position: relative;
  top: -10px;
  left: -2px;
  width: 380px;
  border-radius: 50%;
}

@keyframes flip {
  0% {
    transform: rotateY(0);
  }
  25% {
    transform: rotateY(90deg);
  }
  50% {
    transform: rotateY(180deg);
  }
  75% {
    transform: rotateY(270deg);
  }
  100% {
    transform: rotateY(360deg);
  }
}

@keyframes flip-text-head {
  0% {
    transform: rotateY(0);
    opacity: 1;
  }
  25% {
    transform: rotateY(90deg);
  }
  50% {
    transform: rotateY(180deg);
    opacity: 0;
  }
  75% {
    transform: rotateY(270deg);
  }
  100% {
    transform: rotateY(360deg);
    opacity: 1;
  }
}

@keyframes flip-text-tail {
  0% {
    transform: rotateY(0);
    opacity: 0;
  }
  25% {
    transform: rotateY(90deg);
  }
  50% {
    transform: rotateY(180deg);
    opacity: 1;
  }
  75% {
    transform: rotateY(270deg);
  }
  100% {
    transform: rotateY(360deg);
    opacity: 0;
  }
}
</style>
