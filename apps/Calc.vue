<template>
  <div class="calculator">
    <input type="text" class="calc-numbers" value="0" >

    <div class="calculator-buttons">
      <button class="btn is-clear span-2 orange operator">C</button>
      <button class="btn orange operator">&larr;</button>
      <button class="btn orange operator">&divide;</button>
      <button class="btn">7</button>
      <button class="btn">8</button>
      <button class="btn">9</button>
      <button class="btn orange operator">x</button>
      <button class="btn">4</button>
      <button class="btn">5</button>
      <button class="btn">6</button>
      <button class="btn orange">-</button>
      <button class="btn">1</button>
      <button class="btn">2</button>
      <button class="btn">3</button>
      <button class="btn orange operator">+</button>
      <button class="btn span-3">0</button>
      <button class="btn orange operator">=</button>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Space+Mono');
.calculator-buttons{
    display:grid;
    grid-template-columns: repeat(4,1fr);
    border:0;
}
.calc-numbers{
    font-family: 'Space Mono', serif;
    background: black;
    color: white;
    font-size: 2em;
    border:0;
    text-align: right;
    width: 100%;
}
.span-2{
    grid-column: span 2;
}
.span-3{
    grid-column: span 3;
}
.btn{
    font-size:1em;
    height: 65px;
    border:1px solid black;
}
.btn:hover{
    background: #fff;
}
.orange{
    background-color:orange;
}
</style>
