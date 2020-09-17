<template>
    <div class="search">
        <h1>Search</h1>
        <input type="text" v-model="query" @keyup="getMovies()">
        <div v-for="result in results" :key="result.id">
            <p>{{result.title}}</p>

            <img v-bind:src="'http://image.tmdb.org/t/p/w500/' + result.poster_path" width="100px">
        </div>
    </div>
</template>

<script>
import axios from "axios"
export default {
    name: "search",
    data () {
        return {
            query: "superman",
            results: " ",
            apiKey: "edbf0621b39a1db6f6ce24db4800ad5c"
        }
    },
    methods: {
        // async getURL() {
        //     let URL = 'https://api.themoviedb.org/3/search/movie?api_key=edbf0621b39a1db6f6ce24db4800ad5c&query=superman'
        //     let response = await fetch(URL)
        //     .then(response => response.json())
        // }
        
        
        getMovies() {
            // const requestOptions = {
            // method: 'GET',
            // headers: { 
            // 'Content-Type': 'application/json',
            // 'Authorization': 'edbf0621b39a1db6f6ce24db4800ad5c'
            // }};
            // fetch('https://api.themoviedb.org/3/search/movie?', requestOptions)
            //     .then(response => response.json())
            //     .then(data => this.postId = data.id);
            // }
            let URL = 'https://api.themoviedb.org/3/search/movie?api_key=edbf0621b39a1db6f6ce24db4800ad5c&query=superman'
            axios.get(URL).then(response => { this.results = response.data.results })
            // this.responseAvailable = false
            // fetch(URL, {
            //     "method": "GET",
            //     "headers": {
            //         "Content-type": "application/json; charset=utf-8"
            //     }
            // }) 
            // .then(response => {
            //     if(response.ok) {
            //         this.results = response
            //         return response.json()

            //     } else {
            //         alert("Server returned " + response.status + " : " + response.statusText)
            //     }
            // })
            // .then(response => {
            //     this.results = response
            //     this.responseAvailable = true
            // })
            // .catch(err => {
            //     console.log(err)
            // })
        }
            
    }
}
</script>

<style scoped>

</style>