<template>
    <section>
        <div class="stars-box"
            v-for="(movie, index) in arrayMovie"
            :key="index"
                
        >
            <span>
                <i class="full fas fa-star"></i>
                <i class="empty far fa-star"></i>
            
            </span>
            
            
            <!-- <h3> 
                Voto: {{Math.ceil((movie.vote_average)/2) === 0 ? 'Non classificabile' : Math.ceil((movie.vote_average)/2)}}
            </h3>-->
        </div>
    </section>
</template>

<script>
export default {
    name: 'Stars',
    props:['arrayMovie'],
}
</script>

<style scoped lang="scss">

    .stars-box{
        span{
            font-size: 20px;

            i.full{
               color: rgb(194, 194, 25); 
            }
        }
        
    }

    
</style>

