<template>
    <header>

        <div class="bar">




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
                    :class="{show:statSearch, close:statSearch === false }"
                    
                    type="text" 
                    placeholder="Cercare film/serie"
                    v-model.trim="searchText"

                >
                    
                
                

                <i 
                    @click="clickShow"
                    class="search-button fas fa-search" 
                    type="submit" 
                    @click.prevent="$emit('perfSearch', searchText)"
                >
                    
                    
                </i>

                <ul>
                    <li>
                        <h4>Bambini</h4>


                    </li>

                    <li>
                        <i class="fas fa-gift"></i>
                    </li>

                    <li>
                        <i class="fas fa-bell"></i>
                    </li>

                    <li>
                        <div class="box-profile"></div>
                    </li>
                </ul>
            </div>
        </div>

    </header>
</template>

<script>
export default {
    name:'Header',
    

    data(){
        return{
            searchText:'',
            statSearch: undefined,
        };
    },
    methods:{
        clickShow(){
            this.statSearch =! this.statSearch;
        }
    }

    
};
</script>

<style scoped lang="scss">

    header{
        background-color: rgba(51, 51, 51, 0.692);
        padding: 9px 70px;
        position: fixed;
        top: 0;
        z-index: 8;
        width: 100%;






        .bar{
            display: flex;
            justify-content: space-between;
            align-items: center;
            


            
                
            .nav-left{
                display: flex;

                img{
                    width: 200px;
                    margin-right: 30px;
                    transition: all .2s ease-in-out;

                    &:hover{
                        transform: scale(1.4);
                    }
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

            .nav-right{
                display: flex;
                align-items: center;
                
                input.show{
                    animation: search-in .3s forwards;

                }

                input.close{
                    animation: search-out .3s forwards;
                }

                @keyframes search-in{
                    0% {
                        width: 0;
                        border: none;
                        padding-left: 0;
                    }
                    100%{
                        width: 299px;
                        border: 1px solid white;
                        padding-left: 10px;
                    }
                }

                @keyframes search-out{
                    0%{
                        width: 299px;
                        border: 1px solid white;
                        padding-left: 10px;
                        
                    }
                    100%{
                        width: 0;
                        border: none;
                        padding-left: 0;
                        
                    }
                }
                .search-button{
                    color: white;
                    cursor: pointer;
                    font-size: 20px;
                    margin: 0 10px;

                    &:active{
                        color: red;
                    }
                }

                

                
                
                ul{
                    display: flex;
                    align-items: center;

                    li{
                        margin: 0 10px;
                    }

                    
                    li h4{
                        text-transform: uppercase;
                        cursor: pointer;

                        &:hover{
                            color: white;
                        }
                        
                    }

                    li i{
                        color: rgba(255, 255, 255, 0.74);
                        font-size: 20px;
                        cursor: pointer;
                        transition: all .2s ease-in-out; 

                        &:hover{
                            transform: scale(1.5);
                            color: rgba(255, 0, 0, 0.63);
                        }
                    }

                    li .box-profile{
                        width: 34px;
                        height: 34px;
                        background-color: gray;
                        cursor: pointer;
                    }
                }
            }

            

            
            
        }
    }
    

</style>