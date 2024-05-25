<template>
    <div id="available-plans">
        <div class="container">
            <h2 class="desktop">Attiva il tuo piano Go oppure Pro</h2>
            <h3 class="mobile">Attiva il tuo piano Go oppure Pro</h3>
            <p class="big grey">Scegli se attivare subito il Piano Go oppure richiedere un preventivo per il Piano Pro al nostro consulente</p>
            <div class="plans-container">
                <div class="left-side">
                    <PricingBalloonBig
                        :name="goPlanElements.name"
                        :price="goPlanElements.price"
                        :vantages="goPlanElements.vantages"
                        :buttonText="goPlanElements.buttonText"
                        :backgroundColor="goPlanElements.backgroundColor"
                    />
                </div>
                <div class="right-side">
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
        padding: 8rem 1.5rem;

        @media screen and (max-width: 767px) {
            padding: 5rem 1rem;
        }

        div.container {
            text-align: center;

            h2,
            h3 {
                margin: auto;
            }

            h2 {
                width: 27%;
            }

            h3 {
                width: 70%;
                margin-bottom: 2rem;
            }

            p {
                width: 37%;
                margin: auto;
                margin-bottom: 6rem;

                @media screen and (max-width: 767px) {
                    width: 90%;
                }
            }

            div.plans-container {
                @include flex(row, center, start, no-wrap);
                gap: 6rem;

                @media screen and (max-width: 767px) {
                    flex-direction: column;
                    gap: 1rem;
                }

                div.left-side,
                div.right-side {
                    width: 100%;
                }
            }
        }
    }
</style>