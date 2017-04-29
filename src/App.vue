<template>
  <div id="app">
    <h1>Meet Vue.js</h1>

    <label for="post">Insira seu post</label>

    <br>

    <!-- Meu input -->
    <input id="post"
           v-model="newPost"
           v-on:keyup.enter="savePost">

    <!-- Botão de salvar -->
    <button v-on:click="savePost">Salvar</button>

    <h2>Meus posts</h2>
    <hr>

    <!-- Lista de posts -->
    <div v-if="posts.length > 0">
      <p v-for="post in posts">{{ post }}</p>
    </div>

    <!-- Aviso quando a lista de posts está vazia -->
    <div v-else>
      <p><strong>Nenhum post encontrado :(</strong></p>
    </div>

  </div>
</template>

<script>
export default {
  name: 'app',

  data () {
    return {
      posts:   [],
      newPost: ''
    }
  },

  methods: {
    savePost() {
      this.posts.push(this.newPost)
      this.newPost = ''
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align:  center;
  color:       #2c3e50;
  margin-top:  3rem;
}

h2 {
  margin-top: 4rem;
}
</style>
