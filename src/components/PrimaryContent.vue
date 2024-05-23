<template>
    <div id="primary-content">
        <div class="desktop">
            <div class="container">
                <div class="left-side">
                    <h1>Il Welfare aziendale a portata di PMI</h1>
                    <p class="big">MySarma nasce con l'obiettivo di supportare le aziende a rispondere concretamente ai bisogni di welfare dei propri dipendenti e collaboratori.</p>
                </div>
                <div class="right-side">
                    <PricingBalloon
                        :name="goPlanElements.name"
                        :price="goPlanElements.price"
                        :vantages="goPlanElements.vantages"
                        :buttonText="goPlanElements.buttonText"
                        :backgroundColor="goPlanElements.backgroundColor"
                    />
                    <p>Cerchi un piano a misura per la tua azienda?</p>
                    <p>Scopri il piano PRO</p>
                </div>
            </div>
        </div>

        <div class="mobile">
            <h2>Il Welfare aziendale a portata di PMI</h2>
            <p class="big">MySarma nasce con l'obiettivo di supportare le aziende a rispondere concretamente ai bisogni di welfare dei propri dipendenti e collaboratori.</p>
            <PricingBalloon 
                :name="goPlanElements.name"
                :price="goPlanElements.price"
                :buttonText="goPlanElements.buttonText"
                :backgroundColor="goPlanElements.backgroundColor"
            />
        </div>
    </div>
</template>

<script>
    import PricingBalloon from './PricingBalloon.vue';
    import { goPlanElements } from '/data/data.json';

    export default {
        name: 'PrimaryContent',

        data() {
            return {
                goPlanElements: goPlanElements
            }
        },

        components: {
            PricingBalloon
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div#primary-content {
        @include flex(row, center, center, wrap);
        background-image: url("/src/assets/balloons.png");
        background-size: cover;
        height: 1024px;
        position: relative;
        padding: 1rem;

        @media screen and (max-width: 767px) {
            background-position: 35%;
            height: 865px;
        }

        div.desktop div.container {
            @include flex(row, center, center, wrap);

            div.left-side {
                width: 60%;
            }

            div.right-side {
                width: 40%;
            }
        }
    }
</style>