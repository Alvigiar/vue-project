<template>
  <transition name="modal">
    <div class="modal-mask" v-if="modal">
      <div class="modal-wrapper" v-on:click.self="$emit('modalBox')">
        <div class="modal-content">
          <div class="modal-box">
            <modal-button v-on:click="$emit('modalBox')"></modal-button>
            <h1>Title</h1>
            <div>Text</div>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
import ModalButton from "./ModalButton.vue";

export default {
  components: { ModalButton },
  props: {
    modal: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style scoped>
.modal-mask {
  position: fixed;
  z-index: 998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}
.modal-content {
  z-index: 999;
  width: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
}
.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}
.modal-box {
  display: grid;
}
.modal-enter-from {
  opacity: 0;
}

.modal-leave-to {
  opacity: 0;
}

.modal-enter-from .modal-container,
.modal-leave-to .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
