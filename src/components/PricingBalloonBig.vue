<template>
    <div class="pricing-ballooon-big" :style="{ backgroundColor: backgroundColor }">
        <h4>{{ name }}</h4>
        <p class="small">a partire da</p>
        <div class="price">
            <span class="big">{{ euro }}</span>
            <div class="cents">
                <span class="small">,{{ cents }}</span>
                <p class="small">+ IVA</p>
            </div>
        </div>
        <p>all'anno / per utente <i class="fa-solid fa-circle-info"></i></p>
        <hr>
        <ul>
            <li v-for="(vantage, index) in vantages" :key="index"><i class="fa-solid fa-circle-check"></i> {{ vantage }}</li>
        </ul>
        <button>{{ buttonText }}</button>
        <p class="grey">Vuoi maggiori informazioni sul piano?</p>
        <p><u><strong>Scopri di più</strong></u></p>
    </div>
</template>

<script>
    export default {
        name: 'PricingBalloonBig',

        data() {
            return {
                price: this.price
            };
        },

        computed: {
            euro() {
                return this.price.slice(0, this.price.indexOf(","));
            },
            cents() {
                return this.price.slice(this.price.indexOf(",") + 1);
            }
        },

        props: {
            name: String,
            price: String,
            vantages: Array,
            buttonText: String,
            backgroundColor: String
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div.pricing-ballooon-big {
        width: 100%;
        color: black;
        padding: 2.5rem 3rem;
        border-radius: 30px;
        margin-bottom: 3rem;
        text-align: center;

        h4, p {
            color: map-get(map-get($colors, Primary), 500);
        }

        h4 {
            margin-bottom: .8rem;
        }

        p.grey {
            color: map-get(map-get($colors, Black), 200);;
        }

        hr {
            margin: 2rem 0;
            border: 2px solid black;
            border-width: 1.5px;
        }

        span {
            color: black;
            font-weight: 800;

            &.big {
                font-size: 4rem;
            }

            &.small {
                font-size: 2rem;
            }
        }

        ul {
            text-align: start;
            margin-bottom: 4rem;

            li {
                font-size: 1.2rem;
                margin-bottom: 1rem;

                i {
                    font-size: 1.6rem;
                    margin-right: .7rem;
                    vertical-align: middle;
                }
            }
        }

        button {
            margin: auto;
            margin-bottom: 3rem;
            font-size: 18px;
            padding: 1rem 4rem;
        }

        div.price {
            @include flex(row, center, center, wrap);

            div.cents {
                @include flex(column, center, center, wrap);
            }
        }
    }
</style>