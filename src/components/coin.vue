<template>
  <div class="coin" :class="{ coinanimation: isPlaying }">
    <div class="head" :class="{ headanimation: isPlaying }"><h1>H</h1></div>
    <div v-if="isPlaying" :class="{ tailanimation: isPlaying }" class="tail">
      <h1>T</h1>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPlaying: false,
    };
  },
};
</script>

<style>
.coin {
  width: 200px;
  height: 200px;
  background-color: rgb(224, 201, 68);
  text-align: center;
  border: 1px solid black;
  border-radius: 50%;
  margin: 100px auto;
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
