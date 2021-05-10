<template>
    <section class="movies">

        <div class="box-movies">
        <ul>
            <li>
                <h3>Titolo</h3>

                <h3>Titolo Originale</h3>

                <h3>Lingua</h3>

                <h3>Voto</h3>
            </li>
        </ul>

        </div>
    </section>
</template>

<script>
import axios from 'axios';
export default {
    name:'Movies',
    data(){
        return{
            apiURLmovies: 'https://api.themoviedb.org/3/search/movie',
            movieList: [],
            loading: true,
        }

    },
    created(){
        this.getMovies()
    },
    methods: {
        getMovies(){
            axios.get(this.apiURLmovies, {
                params: {
                    api_key:'8c6d856864a9db7703ff46ed6c4bd7bf',
                    query: 'fantozzi',
                }
            })
            .then(result => {
                console.log(result.data);
            })
            .catch(error => {
                console.log('Errore', error);
            });
        }
    }
}
</script>

<style>

</style>