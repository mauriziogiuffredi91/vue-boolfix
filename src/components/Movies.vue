<template>
    <section class="movies">

        
        <h2>Nerdflix a casa tua</h2>
        
        
        <div class="contain"
            v-for="(movie, index) in arrayMovie"
            :key="index"
            
            
        >

            <img 
                :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" 
                alt="Immagine non trovata"
                
            >

            
            <ul
               class="box-movies" 
            
            
            >



                
                
                
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

                    
                    
                    <i class="fas fa-star"
                        :class="{activeStar:Math.ceil((movie.vote_average)/2) >= 1}"

                    ></i>
                    <i class="fas fa-star"
                        :class="{activeStar:Math.ceil((movie.vote_average)/2) >= 2}"
                    ></i>
                    <i class="fas fa-star"
                        :class="{activeStar:Math.ceil((movie.vote_average)/2) >= 3}"
                    
                    ></i>
                    <i class="fas fa-star"
                        :class="{activeStar:Math.ceil((movie.vote_average)/2) >= 4}"
                    
                    ></i>
                    <i class="fas fa-star"
                        :class="{activeStar:Math.ceil((movie.vote_average)/2) >= 5}"
                    ></i>
                
                    
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
    .movies{
        max-width: 1600px;
        margin: 0 auto;
        margin-top: 20px;
    
        .box-movies{
            flex-basis: calc(100%/5);
            
            


            li .flag{
                width: 30px;
                

            }

            i{
                color: gray;
                font-size: 20px;
            }


            i.activeStar{
                color: #ff0022cc;
            }
            
        }
    }


</style>
                        
                        
                     
                    
                



                
                
                
                    
                
                


                
                
                
                    

                    

                    
                
                
                


    
                    
                    
                    
                
            

            
                
            
                
            
                

                
            
        

    
    
    

        
    

    