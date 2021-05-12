<template>
  <div id="app">
    <Header @perfSearch="getProduct"/>
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
      apiURL: 'https://api.themoviedb.org/3/search/',
      apiKey: '8c6d856864a9db7703ff46ed6c4bd7bf',
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
    getProduct(element){
      if(element === ''){
        this.movieList = [];
        this.serieList = [];
      }else{

        const apiParametri = {
          api_key: this.apiKey,
          query: element,
          language: 'it-IT',
        };

        // Call API movie
        axios.get(this.apiURL + 'movie', {
          params: apiParametri,
            
          
        }).then(res => {
          console.log(res.data.results);
          this.movieList = res.data.results;
        })
        .catch(err => {
          console.log('Errore', err);
        });

        //Call API serie tv
        axios.get(this.apiURL + 'tv', {
          params: apiParametri,


        }).then(res => {
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
