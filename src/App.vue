<template>
  <h1>Likes</h1>
  <div class="likes">
    <button v-on:click="addLikes">+</button>
    <button @click="addDislikes">-</button>
    <div>Likes: {{ likes }}</div>
    <div>Dislikes: {{ dislikes }}</div>
  </div>

  <hr />
  <h1>Massive</h1>
  <div class="posts">
    <div class="posts-box" v-for="post in posts">
      <div>Id: {{ post.id }}</div>
      <div>Title: {{ post.title }}</div>
      <div>Body: {{ post.body }}</div>
    </div>
  </div>

  <hr />
  <h1>Next</h1>
</template>



<script>
export default {
  data() {
    return {

      // 1. likes
      likes: 0,
      dislikes: 0,

      // 2. posts/massive
      posts: [
        { id: 1, title: 'Title 1', body: 'Body 1' },
        { id: 2, title: 'Title 2', body: 'Body 2' },
        { id: 3, title: 'Title 3', body: 'Body 3' }
      ]
    }
  },

  // 1. likes
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
body {
  margin: 0;
  padding: 0;
  display: grid;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.likes {
  display: grid;
  justify-content: center;
  padding: 50px;
  margin-bottom: 100px;
  background-color: rgba(75, 50, 50, 0.5);
  border: 2px solid rgba(73, 30, 30, 0.5);
  border-radius: 6px;
}

.posts {
  display: grid;
  gap: 15px;
  margin-bottom: 50px;
}
.posts-box {
  padding: 20px;
  border: 2px solid brown;
  border-radius: 6px;
}
</style>
