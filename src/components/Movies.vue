<template>
    <div>
        <div class="main" v-for="result in results" :key="result.id">
            <p>{{result.title}}</p>
            <img v-bind:src="'http://image.tmdb.org/t/p/w500/' + result.poster_path" width="100px">
        </div>
    </div>
</template>


<script>
export default {
    name: "Movies"
}
</script>

