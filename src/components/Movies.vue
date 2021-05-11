<template>
    <section class="movies">

        
        
        
        <div
            v-for="(movie, index) in arrayMovie"
            :key="index"
            class="box-movies"

        
        > 
            
        
            <ul>
                <li> <h3>Titolo: {{movie.title}}</h3> </li>
                    
                <li><h3>Titolo originale: {{ movie.original_title}}</h3></li> 

                <li v-if="flagsList.includes(movie.original_language)"
                >   
                    <h3>
                        Lingua: <img :src="require(`@/assets/img/${movie.original_language}.png`)" alt="flags">
                    </h3>
                </li>

                <li><h3>Voto: {{movie.vote_average}}</h3></li>
                
                


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
    }

    
};
</script>

<style lang='scss' scoped>

    .box-movies ul{
        margin: 20px 0;
        border: 1px solid black;
    }


</style>
    
                    
                    
                    
                
            

            
                
            
                
            
                

                
            
        

    
    
    

        
    

    