<template>
    <section>
        <a >

            <h2>Cosa vuoi guardare ora?</h2>
            <img src="https://fontmeme.com/permalink/210514/a23b97752ded4f74fe9b7965e1872cce.png" alt="netflix-font" border="0">
        </a>
    </section>
</template>

<script>
export default {
    name:'Start',
}
</script>

<style scoped lang="scss">
    section{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;

        a{
            text-decoration: none;
            img{
                cursor: pointer;
                width: 1000px;
                height: 110px;
                margin: 15px;
            }
        }
    }


</style>