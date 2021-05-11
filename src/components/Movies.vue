<template>
    <section class="movies">

        
        
        
        <div
            v-for="(movie, index) in arrayMovie"
            :key="index"
            class="box-movies"

        
        > 
            

            <ul>

                <li>
                    <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt="img prodotto">
                </li>
                <li> <h3>Titolo: {{movie.title == null ? movie.name : movie.title}}</h3> </li>
                    
                <li><h3>Titolo originale: {{ movie.original_title == null ? movie.original_name : movie.original_title}}</h3></li> 

                <li v-if="flagsList.includes(movie.original_language)"
                >   
                    <h3>
                        Lingua: <img class="flag" :src="require(`@/assets/img/${movie.original_language}.png`)" alt="flags">
                    </h3>
                </li>
                <li v-else
                    
                >
                    <h3>
                        Lingua: {{movie.original_language}}
                    </h3>

                </li>
                <li
                    v-for="(star, index) in Math.ceil((movie.vote_average)/2)"
                    :key="index"
                
                >

                    <!-- ci vogliono le stelle al posto dei h3 font awesome -->
                    <h3>Voto: {{Math.ceil((movie.vote_average)/2) === 0 ? 'Non classificabile' : Math.ceil((movie.vote_average)/2)}}</h3>
                
                </li>
                
                


            </ul>
                
                
        </div>
                
    </section>
</template>

<script>



export default {
    name:'Movies',
    props:['arrayMovie'],

    data(){
        return{
            flagsList:['it', 'en'],
            votoBase: 0,
             
        }

    },
    computed:{
        
        getVote(array, voto){
            array = this.arrayMovie;
            voto = this.votoBase;
           
            return console.log(voto);
            
            //this.arrayMovie.movie.vote_average = this.voto;
            //number = this.arrayMovie.movie.vote_average;
            
            //return Math.ceil((number)/2) === 0 ? 'Non classificabile' : Math.ceil((number)/2);
        }
    }

    
};
</script>

<style lang='scss' scoped>

    .box-movies ul{
        margin: 20px 0;
        border: 1px solid black;

        li .flag{
            width: 30px;
            
        }
    }


</style>
    
                    
                    
                    
                
            

            
                
            
                
            
                

                
            
        

    
    
    

        
    

    