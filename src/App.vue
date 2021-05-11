<template>
  <div id="app">
    <Header @perfSearch="getMovies"/>
    <Movies :arrayMovie="movieList.concat(serieList)" />
    
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue'
import Movies from '@/components/Movies.vue'
export default {
  name: 'App',
  components: {
    Header,
    Movies,
  },
  data(){
    return{
      apiURLseries: 'https://api.themoviedb.org/3/search/tv',
      apiURLmovies: 'https://api.themoviedb.org/3/search/movie',
      movieList: [],
      serieList:[],
      //searchingMovies: '', per un eventuale reset
      
    }

  },
  
  /*funzione di ritorno a vuoto input */

  /*
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

  */
  

  methods: {
    getMovies(element){
      if(element === ''){
        this.movieList = [];
        this.serieList = [];
      }else{

        // Call API movie
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
          console.log('Errore', err);
        });
  
  
        //Call API Serie
        axios.get(this.apiURLseries, {
          params: {
            api_key: '8c6d856864a9db7703ff46ed6c4bd7bf',
            query: element,
            language: 'it-IT',
            /* bastava davvero mettere element, ossia il parametro della funzione al posto di this.search, eravamo vicini*/
          }
        })
        .then(res => {
          console.log(res.data.results);
          this.serieList = res.data.results;
        })
        .catch(err => {
          console.log('Errore', err);
        });
      }

    },


    /*funzione di ritorno a vuoto input*/ 

    /*
    searchFilm(text){
      console.log(text);

      this.searchingMovies = text;

    }

    */
  },

    
}
</script>


<style lang="scss">

</style>
