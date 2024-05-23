<template>
    <div class="pricing-balloon-big" :style="{ backgroundColor: backgroundColor }">
        <p class="big">{{ name }}</p>
        <p>a partire da</p>
        <p>{{ price }}</p>
        <p>all'anno per utente</p>
        <hr>
        <ul>
            <li v-for="(vantage, index) in vantages" :key="index">{{ vantage }}</li>
        </ul>
        <button>{{ buttonText }}</button>
        <p>Vuoi maggiori informazioni sul piano?</p>
        <p>Scopri di più</p>
    </div>
</template>

<script>
    export default {
        name: 'PricingBalloonBig',

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

    div.pricing-balloon-big {
        width: 401px;
        height: 697px;
        padding: 1rem;
        border-radius: 10px;
    }
</style>