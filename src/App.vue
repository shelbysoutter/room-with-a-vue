<template>
  <div id="app">
    <Header />
    <Movies v-bind:movies="movies"/>
  </div>
</template>

<script>
import Header from './components/layout/Header.vue'
import Movies from './components/Movies.vue'

export default {
  name: 'App',
  components: {
    Header,
    Movies
  },
  data() {
    return {
      movies: [
        {

        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>
