<template>
    <section class="main-container">

        
        <div 
            
            v-show="startNet"
            class="empty"
        >
            

            <Start 
                
                
            />

        </div>
        


        <Notfound v-show="foundError" />


        
        <div 
            
            class="contain"
        >

            <div class="contain-little"
                v-for="(movie, index) in arrayMovie"
                :key="index"
                
                
            >

                <img 
                    class="poster"
                    v-if="movie.poster_path"
                    :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" 
                    
                    
                >

                <img 
                    class="poster"
                    v-else
                    src="@/assets/img/poster-placeholder.png" 
                >

                
                <ul class="box-movies">
                 
                
                
                



                    
                    
                    
                    <li> <h4>Titolo: {{movie.title == undefined ? movie.name : movie.title}}</h4> </li>
                        
                    <li><h4>Titolo originale: {{ movie.original_title == undefined ? movie.original_name : movie.original_title}}</h4></li> 

                    <li
                        v-if="movie.overview !== '' "
                    >
                        <h4>Overview: {{movie.overview}}</h4>
                        
                    </li>

                    <li v-else>
                        <h4>Overview non disponibile</h4>
                    </li>
                        

                    <li v-if="flagsList.includes(movie.original_language)"
                        class="flag-position"
                    >   
                        <h4>
                            Lingua: <img class="flag" :src="require(`@/assets/img/${movie.original_language}.png`)" alt="flags">
                        </h4>
                    </li>
                    <li v-else
                        
                    >
                        <h4>
                            Lingua: {{movie.original_language}}
                        </h4>

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

        </div>

        
                
    </section>
</template>

<script>
import Start from '@/components/Start.vue'
import Notfound from '@/components/Notfound.vue'




export default {
    name:'Movies',
    props:['arrayMovie', 'foundError', 'startNet' ],
    
    components:{
        Notfound,
        Start,
        
    },
    
        
    data(){
        return{
            flagsList:['it', 'en'],
            
             
        }

    },
    

    
};
</script>

<style lang='scss' scoped>
    
    
    
    .contain{
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    
    
    
        .contain-little{
            position: relative;
            flex-basis: calc(100%/ 5);
            margin-right: 20px;
            
            &:hover .box-movies{
                display: block;
                
            }

            .poster{
                width: 300px;
                height: 500px;
            }
            
            .box-movies{
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                background-color: rgba(0, 0, 0, 0.71);
                height: 100%;
                width: 100%;
                padding: 5%;
                display: none;
                overflow-y: auto;
                
                
                .flag-position h4{
                    display: flex;
                    
                }

                li .flag{
                    width: 30px;
                    margin-left: 10px;
                    

                }

                i{
                    color: gray;
                    font-size: 20px;
                }


                i.activeStar{
                    color: #ff0022cc;
                    margin: 0 5px;
                }
                i.fas {
                    margin-left: 5px;
                }
                
                i.activeStar:first-of-type{
                    margin-left: 0;
                }
            }
        }
    
    }


    



    
        
    


</style>
                        
                        
                     
                    
                



                
                
                
                    
                
                


                
                
                
                    

                    

                    
                
                
                


    
                    
                    
                    
                
            

            
                
            
                
            
                

                
            
        

    
    
    

        
    

    