<template>
  <div id="app">
    <Header @perfSearch="getProduct"/>
    <Movies :arrayMovie="movieList.concat(serieList)" :foundError="notFoundmovie && notFoundserie" />
    
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
      
      notFoundmovie: false,
      notFoundserie: false,
      
    }

  },
  
  
  

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
          this.notFoundmovie = this.movieList.length === 0;
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
          this.notFoundserie = this.serieList.length === 0;
        })
        .catch(err => {
          console.log('Errore', err);
        });
      }

        
        
        
  
  
        
        

    },


    
  },

    
}
</script>


<style lang="scss">

@import '~@fontsource/farro/500.css';
@import '@/stili/main';


  
</style>
