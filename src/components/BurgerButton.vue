<template>
  <!-- v-on:click по клику происходит $emit('modalToggle') вызов функции из родительского компонента -->
  <div class="burger burger-box" v-on:click="$emit('modalToggle')">
    <!-- v-bind:class привязка к классу элемента, происходит добавление класса из пропса modal (true/false) -->
    <div class="burger-box__toggle" v-bind:class="{ cross: modal }">
      <span></span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["modal"],
};
</script>

<style scoped>
.burger-box__toggle.cross > span {
  background-color: white;
}

.burger-box__toggle.cross > span::before {
  background-color: red;
  transform: rotate(45deg);
}

.burger-box__toggle.cross > span::after {
  background-color: red;
  transform: translateY(-9px) rotate(-45deg);
}

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
