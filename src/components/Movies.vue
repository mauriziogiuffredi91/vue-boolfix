<template>
    <section class="movies">

        <div class="search-box">
            <Search @perfSearch="getMovies"/>
        </div>
        <div
            v-for="(movie, index) in filterMovies"
            :key="index"
            class="box-movies"

        
        > 
            
        
            <ul>
                <li> <h3>Titolo: {{movie.title}}</h3> </li>
                    
                <li><h3>Titolo originale: {{ movie.original_title}}</h3></li> 

                <li><h3>Lingua: {{movie.original_language}}</h3></li>

                <li><h3>Voto: {{movie.vote_average}}</h3></li>
                
                


            </ul>
                
                
        </div>
                
                    
                    
                    
                
            

            
                
            
                
            
                

                
            
        

    </section>
</template>

<script>
import axios from 'axios';
import Search from '@/components/Search.vue';
export default {
    name:'Movies',
    components: {
        Search,
    },
    data(){
        return{
            apiURLmovies: 'https://api.themoviedb.org/3/search/movie',
            movieList: [],
            
            searchingMovies:'',
        }

    },
    computed:{
        filterMovies(){
            if(this.searchingMovies === ''){
                return this.movieList;
            }

            return this.movieList.filter(element => {
                return element.title.toLowerCase().includes(this.searchingMovies.toLowerCase());
            })
        }
    },
    
    methods: {
        getMovies(element){
            // Call API
            axios.get(this.apiURLmovies, {
                params: {
                    api_key: '8c6d856864a9db7703ff46ed6c4bd7bf',
                    query: element,
                    language: 'it-IT',
                    /* bastava davvero mettere element, ossia il parametro della funzione al posto di this.search, eravamo vicini*/
                }
            })
            .then(res => {
                console.log(res.data.results);
                this.movieList = res.data.results;
            })
            .catch(err => {
                console.log(err);
            });
        },

        /*Funzione che serve per tornare in uno stato vuoto*/
        searchElement(text){
            console.log('test', text);

            this.searchingMovies = text;
        },
    

    },
};
</script>

<style lang='scss' scoped>
    .box-movies ul{
        margin: 20px 0;
        border: 1px solid black;
    }

</style>