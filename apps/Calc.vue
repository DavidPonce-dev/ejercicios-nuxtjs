<template>
  <div class="calculator">
    <input type="text" class="calc-numbers" value="0">

    <div class="calculator-buttons">
      <div class="btn is-clear span-2 orange operator">C</div>
      <div class="btn orange operator">&larr;</div>
      <div class="btn orange operator">&divide;</div>
      <div class="btn">7</div>
      <div class="btn">8</div>
      <div class="btn">9</div>
      <div class="btn orange operator">x</div>
      <div class="btn">4</div>
      <div class="btn">5</div>
      <div class="btn">6</div>
      <div class="btn orange">-</div>
      <div class="btn">1</div>
      <div class="btn">2</div>
      <div class="btn">3</div>
      <div class="btn orange operator">+</div>
      <div class="btn span-3">0</div>
      <div class="btn orange operator">=</div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {}
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Space+Mono");
.calculator{
    height: 100%;
}
.calculator-buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  border: 0;
  height: calc(100% - 48px);
}
.calc-numbers {
  font-family: "Space Mono", serif;
  background: black;
  color: white;
  font-size: 2em;
  border: 0;
  text-align: right;
  width: 100%;
}
.span-2 {
  grid-column: span 2;
}
.span-3 {
  grid-column: span 3;
}
.btn {
  font-size: 1em;
  height: 100%;
  border: 1px solid black;
    background: #fff;
}
.btn:hover {
  background: rgb(24, 24, 24);
  color: #fff;
}
.orange {
  background-color: orange;
}
</style>
