<script setup lang="ts"></script>
<template>
  <main>
    <div class="box">
      親要素（.box）
      <div class="box__inner">子要素（.box__inner）</div>
    </div>
    <article>
      <p>I want to be red and larger than the other text.</p>
      <p>I want to be normal sized and the default color.</p>
    </article>
    <div data-type="primary">primary</div>
    <div data-type="secondary">secondary</div>
    <ul>
      <li>11111111111</li>
      <li>22222222222</li>
      <li>33333333333</li>
    </ul>
  </main>
</template>
<style lang="scss" scoped>
.box {
  width: 500px;
  height: 200px;
  border: 2px dashed #666;

  &__inner {
    width: 100%;
    padding: 10px;
    background-color: #fff4c3;
    border: 3px solid #ff8410;
    box-sizing: border-box;
  }
}
article p:first-of-type {
  color: red;
  font-size: 1.5em;
}
[data-type="primary"] {
  color: red;
}
/* 偶数段落を対象とする */
p:nth-child(even) {
  background: floralwhite;
}
li::marker {
  color: red;
}
::selection {
  background: black;
  color: white;
}
</style>
