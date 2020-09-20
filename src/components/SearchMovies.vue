<template>
    <div class="search-area">
        <h1>Search</h1>
        <input type="text" v-model="query" @keyup="getMovies(query)">
        <div v-if="this.query != ''" class="main-movie-box">
            <div class="individual-movie" v-for="result in results" :key="result.id"> 
                <p>{{result.title}}</p>
                <img class="image" v-if="result.poster_path != null" v-bind:src="'http://image.tmdb.org/t/p/w500/' + result.poster_path" width="100px">
                <img class="image" v-if="result.poster_path == null && result.title != null" src='https://thumbs.dreamstime.com/b/no-image-available-icon-flat-vector-no-image-available-icon-flat-vector-illustration-132482953.jpg' width="100px">
                <div class="movie-text-location">
                    <div class="movie-text">{{result.overview}}</div>
                </div>
            </div>
        </div>
        <p v-if="this.results.length == 0 && this.query != 0">Sorry! There are no movies available matching your search.</p>
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
* {
    box-sizing: border-box;
}
.main-movie-box {
    display: grid;
    /* justify-items: stretch; */
    grid-template-columns: 20% 20% 20% 20% 20%;
    padding-top: 5%;
    column-gap: 5px;
    row-gap: 15%;
}
.individual-movie:hover .movie-text-location {
    opacity: 1;
}
.individual-movie:hover .image {
    opacity: 0.3;
    transition: .5s ease;
}
.individual-movie {
    display: block;
    width: 100%;
}
.movie-text-location {
    transition: .5s ease;
    opacity: 0;
    position: absolute;   
}
.movie-text {
    color: white;
}
.search-area {
    min-height: 100vh;
    overflow: hidden;
    position: relative;
    padding-bottom: 175px;
}
</style>