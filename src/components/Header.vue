<template>
    <header>

        <div class="nav-left">
            <a href="https://fontmeme.com/netflix-font/">
                <img src="https://fontmeme.com/permalink/210510/118a19bf945a6213de0a49fdb190e65d.png" alt="netflix-font" border="0">
            </a>

        </div>
        <div class="nav-right">
            <input 
            type="text" 
            placeholder="text here"
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
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px;

        .nav-left{
            img{
                width: 200px;
            }
        }
        
    }
    

</style>