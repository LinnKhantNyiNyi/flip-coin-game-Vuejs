<template>
  <h4>Give Your Best Guess!</h4>
  <div class="guess-container">
    <button class="guess-btn">Head</button>
    <button class="guess-btn">Tail</button>
  </div>
</template>

<script>
export default {};
</script>

<style>
.guess-container {
  width: 500px;
  padding: 50px 0;
  margin: 0 auto;
  background-color: rgb(155, 154, 154);
  border-radius: 10px;
}
.guess-btn {
  width: 30%;
  height: 50px;
  margin: 0 20px;
  border-radius: 10px;
  border: 0;
  cursor: pointer;
  background-color: rgb(105, 194, 105);
  font-size: 15px;
}
</style>
