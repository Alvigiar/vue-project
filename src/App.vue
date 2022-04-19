<template>
  <div class="content-box">
    <!-- v-bind:modal с помощью этого передается информация modalIsShow (false), в последствии дочерние могут её прослушивать -->
    <!-- v-on:modal-toggle при изменении состояния происходит вызов функции modalToggle -->
    <burger-button
      v-bind:modal="modalIsShow"
      v-on:modal-toggle="modalToggle"
    ></burger-button>
    <modal v-bind:modal="modalIsShow" v-on:modal-box="modalToggle"></modal>
    <div class="login">
      <button>Вход</button>
      <button>Регистрация</button>
    </div>
  </div>
</template>

<script>
// импорт дочерних элементов
import BurgerButton from "./components/BurgerButton.vue";
import Modal from "./components/Modal.vue";

export default {
  // происходит подключение компонентов
  components: { BurgerButton, Modal },
  data() {
    return {
      modalIsShow: false, // состояние
    };
  },
  methods: {
    modalToggle() {
      // элементу modalIsShow присваиваем значение, противоположное его значению
      this.modalIsShow = !this.modalIsShow;
      console.log("modalToggle");
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
.login {
  display: grid;
}
</style>
