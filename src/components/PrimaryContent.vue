<template>
    <div id="primary-content">
        <div class="desktop">
            <div class="container">
                <div class="left-side">
                    <h1>Il Welfare aziendale a portata di PMI</h1>
                    <p class="big">MySarma nasce con l'obiettivo di supportare le aziende a rispondere concretamente ai bisogni di welfare dei propri dipendenti e collaboratori.</p>
                </div>
                <div class="right-side">
                    <PricingBalloonBig
                        :name="goPlanElements.name"
                        :price="goPlanElements.price"
                        :vantages="goPlanElements.vantages"
                        :buttonText="goPlanElements.buttonText"
                        :backgroundColor="goPlanElements.backgroundColor"
                    />
                    <p>Cerchi un piano a misura per la tua azienda?</p>
                    <p><u>Scopri il <strong>piano PRO</strong></u></p>
                </div>
            </div>
        </div>

        <div class="mobile">
            <h2>Il Welfare aziendale a portata di PMI</h2>
            <p class="big">MySarma nasce con l'obiettivo di supportare le aziende a rispondere concretamente ai bisogni di welfare dei propri dipendenti e collaboratori.</p>
            <p class="small">Da oggi puoi attivare il tuo piano welfare direttamente online ed in pochi semplici passaggi grazie al Piano GO!</p>
            <PricingBalloonSmall
                :name="goPlanElements.name"
                :price="goPlanElements.price"
                :buttonText="goPlanElements.buttonText"
                :backgroundColor="goPlanElements.backgroundColor"
            />
        </div>
    </div>
</template>

<script>
    import { goPlanElements } from '/data/data.json';
    import PricingBalloonBig from './PricingBalloonBig.vue';
    import PricingBalloonSmall from './PricingBalloonSmall.vue';

    export default {
        name: 'PrimaryContent',

        data() {
            return {
                goPlanElements: goPlanElements
            }
        },

        components: {
            PricingBalloonBig,
            PricingBalloonSmall
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
        position: relative;
        color: white;
        padding: 3rem 1rem 0;

        @media screen and (max-width: 767px) {
            background-position: 35%;
            padding-bottom: 16rem;
        }

        div.desktop div.container {
            @include flex(row, end, center, wrap);

            div.left-side {
                width: 50%;
                margin-bottom: 15rem;
                margin-right: 10rem;

                @media screen and (min-width: 768px) and (max-width: 1199px) {
                    margin-right: 0;
                }

                h1 {
                    margin-bottom: 4rem;
                    width: 88%;
                }

                p {
                    width: 88%;
                }
            }

            div.right-side {
                @include flex(column, center, end, no-wrap);
                padding: 6rem 0;
                width: 30%;

                @media screen and (min-width: 768px) and (max-width: 1199px) {
                    width: 50%;
                }

                p {
                    align-self: center
                }
            }
        }

        div.mobile {
            h2 {
                width: 60%;
                margin-bottom: 2.5rem;
            }

            p {
                margin-bottom: 2rem;
            }
        }
    }
</style>