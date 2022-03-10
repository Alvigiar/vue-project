<template>
  <div class="likes">
    <button v-on:click="addLikes">+</button>
    <button @click="addDislikes">-</button>
    <div>Likes: {{ likes }}</div>
    <div>Dislikes: {{ dislikes }}</div>
  </div>
</template>



<script>
export default {
  data() {
    return {
      likes: 0,
      dislikes: 0,
    }
  },
  methods: {
    addLikes() {
      this.likes += 1;
    },
    addDislikes() {
      this.dislikes += 1;
    }
  }
}
</script>



<style>
.likes {
  display: grid;
  justify-content: center;
  padding: 50px;
  margin-bottom: 100px;
  background-color: rgba(75, 50, 50, 0.5);
  border: 2px solid rgba(73, 30, 30, 0.5);
  border-radius: 6px;
}
</style>
