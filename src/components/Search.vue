<template>
    <section>
        <input 
            type="text" 
            placeholder="text here"
            v-model="searchText"
        >

        <button 
            class="searchBtn" 
            type="submit" 
            @click.prevent="$emit('perfSearch', searchText)"
        >
            Search
        </button>
    </section>
</template>

<script>
export default {
    name:'Search',
    data(){
        return{
            searchText:'',
        };
    },
};
</script>

<style scoped>

</style>