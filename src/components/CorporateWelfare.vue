<template>
    <div id="corporate-welfare">
        <div class="container">
            <h1>Welfare aziendale?</h1>
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
        div.container {
            text-align: center;

            div.cards-container {
                @include flex(row, center, center, no-wrap);

                @media screen and (max-width: 767px) {
                    flex-direction: column;
                }
            }
        }
    }
</style>