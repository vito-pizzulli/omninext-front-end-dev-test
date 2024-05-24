<template>
    <div class="pricing-balloon-small" :style="{ backgroundColor: backgroundColor }">
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
        <p><i class="fa-solid fa-chevron-down"></i></p>
        <button>{{ buttonText }}</button>
        <p class="grey">Vuoi maggiori informazioni sul piano?</p>
        <p><u><strong>Scopri di più</strong></u></p>
    </div>
</template>

<script>
    export default {
        name: 'PricingBalloonSmall',

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
            buttonText: String,
            backgroundColor: String
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div.pricing-balloon-small {
        width: 90%;
        padding: 2rem;
        border-radius: 30px;
        position: absolute;
        left: 50%;
        top: 100%;
        transform: translate(-50%, -50%);
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
            margin: 1rem 0;
            border: 2px solid black;
        }

        i {
            color: map-get(map-get($colors, Primary), 200);
            margin-bottom: 1rem;
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

        button {
            margin: auto;
            margin-bottom: 2rem;
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