<template>
  <div id="app">
    <Header />
    <Movies v-bind:movies="movies"/>
    <Footer />
  </div>
</template>

<script>
import Header from './components/layout/Header.vue';
import Footer from './components/layout/Footer.vue';
import Movies from './components/Movies.vue';

export default {
  name: 'App',
  components: {
    Header,
    Movies,
    Footer
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
  color: #EAEBEB;
  background-color: #292B35;
}
body {
  margin: 0px !important;
}

</style>
