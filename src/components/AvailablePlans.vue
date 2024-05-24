<template>
    <div id="available-plans">
        <div class="container">
            <h2>Attiva il tuo piano Go oppure Pro</h2>
            <p class="big">Scegli se attivare subito il Piano Go oppure richiedere un preventivo per il Piano Pro al nostro consulente</p>
            <div class="plans-container">
                <PricingBalloonBig
                    :name="goPlanElements.name"
                    :price="goPlanElements.price"
                    :vantages="goPlanElements.vantages"
                    :buttonText="goPlanElements.buttonText"
                    :backgroundColor="goPlanElements.backgroundColor"
                />
                <PricingBalloonBig
                    :name="proPlanElements.name"
                    :price="proPlanElements.price"
                    :vantages="proPlanElements.vantages"
                    :buttonText="proPlanElements.buttonText"
                    :backgroundColor="proPlanElements.backgroundColor"
                />
            </div>
        </div>
    </div>
</template>

<script>
    import { goPlanElements, proPlanElements } from '/data/data.json';
    import PricingBalloonBig from './PricingBalloonBig.vue';

    export default {
        name: 'AvailablePlans',

        data() {
            return {
                goPlanElements: goPlanElements,
                proPlanElements: proPlanElements
            }
        },

        components: {
            PricingBalloonBig
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div#available-plans {
        div.container {
            text-align: center;

            div.plans-container {
                @include flex(row, center, center, no-wrap);

                @media screen and (max-width: 767px) {
                    flex-direction: column;
                }
            }
        }
    }
</style>