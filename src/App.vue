<template>
  <div class="main" id="app">
    <Header />
    <SearchMovies />
    <Movies v-bind:movies="movies"/>
  </div>
</template>

<script>
import Header from './components/layout/Header.vue'
import SearchMovies from './components/SearchMovies.vue'
import Movies from './components/Movies.vue'

export default {
  name: 'App',
  components: {
    Header,
    SearchMovies,
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

* {
    box-sizing: border-box;
}
.main {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1 fr));
}
.child-box {
    display: block;
    box-shadow: -1px 0px 0px rgba(0,0,0,0.06);
}

</style>
