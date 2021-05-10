<template>
    <section class="movies">
        movies here
    </section>
</template>

<script>
import axios from 'axios';
export default {
    name:'Movies',
    data(){
        return{
            apiURL:
            movieList: [],
            loading: true,
        }
    }
}
</script>

<style>

</style>