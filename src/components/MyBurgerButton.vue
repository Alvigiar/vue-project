<template>
  <div class="burger burger-box">
    <div class="burger-box__toggle">
      <span></span>
    </div>
  </div>
</template>

<script></script>

<style scoped>
.burger-box {
  position: relative;
  width: 30px;
  height: 20px;
  z-index: 2;
  justify-self: end;
  cursor: pointer;
}
.burger-box__toggle {
  width: 100%;
  height: 2px;
}
.burger-box__toggle > span::before,
.burger-box__toggle > span,
.burger-box__toggle > span::after {
  position: absolute;
  width: 100%;
  height: 2px;
  transition: 0.3s;
  background-color: black;
}
.burger-box__toggle > span::before {
  content: "";
  top: 9px;
}
.burger-box__toggle > span::after {
  content: "";
  top: 18px;
}
</style>
