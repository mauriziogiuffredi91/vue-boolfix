<template>
    <section class="movies">

        
        
        
        <div>
            
            <ul
                v-for="(movie, index) in arrayMovie"
                :key="index"
                class="box-movies"
            
            
            >

                <li>
                    <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt="Immagine non trovata">
                </li>
                <li> <h3>Titolo: {{movie.title == undefined ? movie.name : movie.title}}</h3> </li>
                    
                <li><h3>Titolo originale: {{ movie.original_title == undefined ? movie.original_name : movie.original_title}}</h3></li> 

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
                
                

                <li>
                    
                    <!-- ci vogliono le stelle al posto dei h3 font awesome -->
                    <h3>Voto: {{Math.ceil((movie.vote_average)/2) === 0 ? 'Non classificabile' : Math.ceil((movie.vote_average)/2)}}</h3>

                    <i class="full fas fa-star"></i>
                    <i class="empty far fa-star"></i>

                    
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
            
             
        }

    },
    

    
};
</script>

<style lang='scss' scoped>

    .box-movies{
        margin: 20px 0;
        border: 1px solid black;

        li .flag{
            width: 30px;


            
        }

        .full{
            color: rgb(182, 182, 16);
        }
    }


</style>
    
                    
                    
                    
                
            

            
                
            
                
            
                

                
            
        

    
    
    

        
    

    