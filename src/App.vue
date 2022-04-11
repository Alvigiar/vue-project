<template>
  <div class="content-box">
    <my-burger-button
      :class="{ circle: classCircle }"
      @click="activeClass"
    ></my-burger-button>
    <div>Простой текст</div>
  </div>
</template>

<script>
import MyBurgerButton from "./components/MyBurgerButton.vue";

export default {
  components: { MyBurgerButton },
  data() {
    return {
      classCircle: false,
    };
  },
  methods: {
    activeClass() {
      this.classCircle = true;
    },
  },
};
</script>

<style>
#app {
  margin: 0;
  padding: 0;
  display: grid;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

.content-box {
  display: grid;
  justify-items: center;
  gap: 30px;
}
.circle {
  display: none;
}
</style>
