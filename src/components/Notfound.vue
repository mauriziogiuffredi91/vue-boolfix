<template>
    <section>

        <div class="container-search">

            

            <h2>Nessun risultato per la tua ricerca.</h2>

            <h3>Suggerimenti:</h3>
            
            

            

            <ul>
                <li>
                    <h3>Prova con parole chiave diverse.</h3>
                </li>

                <li>
                    <h3>Cerchi un film o un programma TV?</h3>
                </li>

                <li>
                    <h3>Prova a usare il titolo di un film o programma TV.</h3>
                </li>
            </ul>
        </div>
        
    </section>
</template>

<script>
export default {
    name: 'Notfound',
}
</script>

<style scoped lang="scss">
    section{
        display: flex;
        justify-content: center;
        .container-search{
            text-align: left;
            
            
            
            
        }
    }

</style>