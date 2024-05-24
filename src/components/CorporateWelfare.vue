<template>
    <div id="corporate-welfare">
        <div class="container">
            <h1 class="desktop">Welfare aziendale?</h1>
            <h2 class="mobile">Welfare aziendale?</h2>
            <p class="big">Te lo diciamo noi se non lo sai</p>
            <div class="cards-container">
                <WelfareCard v-for="(welfareElement, index) in welfareElements" :key="index"
                    :label="welfareElement.label"
                    :text="welfareElement.text"
                    :imgUrl="welfareElement.imgUrl"
                />
            </div>
        </div>
    </div>
</template>

<script>
    import { welfareElements } from '/data/data.json';
    import WelfareCard from './WelfareCard.vue';

    export default {
        name: 'CorporateWelfare',

        data() {
            return {
                welfareElements: welfareElements
            }
        },

        components: {
            WelfareCard
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div#corporate-welfare {
        padding: 8rem 1rem;

        @media screen and (max-width: 767px) {
            padding: 3rem 1rem;
        }

        div.container {
            text-align: center;

            h1,
            h2 {
                margin-bottom: 1rem;
            }

            p {
                color: grey;
                margin-bottom: 8rem;

                @media screen and (max-width: 767px) {
                    margin-bottom: 4rem;
                }
            }

            div.cards-container {
                @include flex(row, center, center, no-wrap);

                @media screen and (max-width: 767px) {
                    flex-direction: column;
                }
            }
        }
    }
</style>