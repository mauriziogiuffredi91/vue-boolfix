<template>
    <section class="movies">

        
        
        
        <div>

            <h2>Nerdflix a casa tua</h2>
            
            <ul
                v-for="(movie, index) in arrayMovie"
                :key="index"
                class="box-movies"
            
            
            >



                
                <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt="Immagine non trovata">
                
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

    .box-movies{
        margin: 20px 0;
        border: 1px solid black;

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


</style>
                        
                        
                     
                    
                



                
                
                
                    
                
                


                
                
                
                    

                    

                    
                
                
                


    
                    
                    
                    
                
            

            
                
            
                
            
                

                
            
        

    
    
    

        
    

    