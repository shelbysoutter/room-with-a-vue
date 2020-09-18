<template>
    <div>
        <SearchMovies />
    </div>
</template>


<script>
import SearchMovies from './SearchMovies.vue';

export default {
    name: "Movies",
    components: {
        SearchMovies
    },
    props: ["results"]
}
</script>

<style scoped>

</style>

