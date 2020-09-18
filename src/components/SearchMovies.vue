<template>
    <div class="search">
        <h1>Search</h1>
        <input type="text" v-model="query" @keyup="getMovies(query)">
        <div v-for="result in results" :key="result.id"> 
            <p>{{result.title}}</p>
            <img v-if="result.poster_path != null" v-bind:src="'http://image.tmdb.org/t/p/w500/' + result.poster_path" width="100px">
            <img v-if="result.poster_path == null && result.title != null" src='https://thumbs.dreamstime.com/b/no-image-available-icon-flat-vector-no-image-available-icon-flat-vector-illustration-132482953.jpg' width="100px">
        </div>
        <p v-if="this.results.length == 0">Sorry! There are no movies available matching your search.</p>
    </div>
</template>

<script>
import axios from "axios";

export default {
    name: "SearchMovies",
    data () {
        return {
            query: "",
            results: " ",
            apiKey: "edbf0621b39a1db6f6ce24db4800ad5c"
        }
    },
    methods: { 
        getMovies(query) {
            let URL = 'https://api.themoviedb.org/3/search/movie?api_key=edbf0621b39a1db6f6ce24db4800ad5c&query=' + query
            axios.get(URL).then(response => { this.results = response.data.results })
        }   
    }
}
</script>

<style scoped>

</style>