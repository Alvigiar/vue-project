<template>
  <div class="btn btn-box">
    <div class="btn-box__toggle">
      <span></span>
    </div>
  </div>
</template>

<script></script>

<style scoped>
.btn-box {
  position: relative;
  width: 30px;
  height: 30px;
  justify-self: end;
  cursor: pointer;
}
.btn-box__toggle {
  width: 100%;
  height: 2px;
}
.btn-box__toggle > span,
.btn-box__toggle > span::before {
  position: absolute;
  width: 100%;
  height: 2px;
  transition: 0.3s;
  background-color: red;
}
.btn-box__toggle > span {
  transform: rotate(45deg) translate(10px, 10px);
}
.btn-box__toggle > span::before {
  content: "";
  top: 9px;
  transform: rotate(-95deg) translate(8px, 0px);
}
</style>
