<template>
    <div id="collaborators-wellness">
        <div class="container">
            <p class="big">Sfrutta al meglio il tuo potenziale e fai crescere</p>
            <h4>il benessere dei tuoi collaboratori</h4>
            <p>Attiva subito un <strong>Piano Go</strong> oppure richiedi un preventivo gratuito per attivare un <strong>Piano Pro</strong>. Il nostro Welfare guru è pronto a consigliarti la migliore soluzione in base alle tue esigenze.</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CollaboratorsWellness',
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div#collaborators-wellness {
        background-image: url("/src/assets/go-plan-pattern.png");
        background-color: map-get(map-get($colors, Primary), 700);
        padding: 8rem 1rem;

        @media screen and (max-width: 767px) {
            padding: 8rem 2rem;
        }

        div.container {
            @include flex(column, center, center, wrap);
            color: map-get(map-get($colors, Black), 50);
            margin: auto;
            text-align: center;

            h4 {
                font-size: 38px;
                margin-bottom: 1.5rem;
            }

            p:first-of-type {
                margin-bottom: 1rem;
            }

            p:last-of-type {
                width: 46%;

                @media screen and (max-width: 767px) {
                    width: 100%;
                }
            }
        }
    }
</style>