<template>
    <div class="search">
        <h1>Search</h1>
        <input type='text' v-model='query' @keyup='getMovies()'>
        <div v-for='result in results' :key='result.id'>
            <p>{{result.original_title}}</p>
            <img v-bind:src="'http://image.tmdb.org/t/p/w500/' + result.poster_path" width='100px'>
        </div>
    </div>
</template>

<script>
// import axios from 'axios'
export default {
    name: 'search',
    data () {
        return {
            query: '',
            results: '',
            apiKey: "edbf0621b39a1db6f6ce24db4800ad5c"
        }
    },
    methods: {
        getMovies() {
            fetch("https://api.themoviedb.org/3/search/movie?${this.apiKey}&query=${this.query}", {
                "method": "GET"
            })
            .then(response => {
                if(response.ok) {
                    return response.json()
                } else {
                    alert("Server returned " + response.status + " : " + response.statusText)
                }
            })
            .then(response => {
                this.result = response.body
            })
            .catch(err => {
                console.log(err)
            })
        }
            
    }
}
</script>