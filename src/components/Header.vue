<template>
    <header>

        <div class="nav-left">
            <a href="https://fontmeme.com/netflix-font/">
                <img src="https://fontmeme.com/permalink/210510/118a19bf945a6213de0a49fdb190e65d.png" alt="netflix-font" border="0">
            </a>

            <ul>
                <li>
                    <h4>Home</h4>
                </li>

                <li>
                    <h4>Serie Tv</h4>
                </li>

                <li>
                    <h4>Film</h4>
                </li>

                <li>
                    <h4>Nuovi e popolari</h4>
                </li>

                <li>
                    <h4>La mia lista</h4>
                </li>
            </ul>

        </div>
        <div class="nav-right">
            <input 
                type="text" 
                placeholder="Cercare film/serie"
                v-model.trim="searchText"

            >
                

            

            <button 
                class="searchBtn" 
                type="submit" 
                @click.prevent="$emit('perfSearch', searchText)"
            >
                
                Search 
            </button>
        </div>
    </header>
</template>

<script>
export default {
    name:'Header',
    

    data(){
        return{
            searchText:'',
        };
    },

    
};
</script>

<style scoped lang="scss">

    
    header{
        background-color: transparent;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px;


        
            
        .nav-left{

            display: flex;
            img{
                width: 200px;
                margin-right: 30px;
            }
            
            ul{
                display: flex;
                align-items: center;
            }

            ul li{
                margin-right: 20px;
                

                h4{
                  cursor: pointer;  
                
                    &:hover{
                        color: white;
                    }
                }
            }


        }

        

        
        
    }
    

</style>