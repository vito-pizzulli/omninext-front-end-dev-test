<template>
    <div class="pricing-balloon-small" :style="{ backgroundColor: backgroundColor }">
        <p class="big">{{ name }}</p>
        <p>a partire da</p>
        <p>{{ price }}</p>
        <p>all'anno per utente</p>
        <hr>
        <button>{{ buttonText }}</button>
        <p>Vuoi maggiori informazioni sul piano?</p>
        <p>Scopri di più</p>
    </div>
</template>

<script>
    export default {
        name: 'PricingBalloonSmall',

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
        width: 401px;
        height: 410px;
        padding: 1rem;
        border-radius: 10px;
        position: absolute;
        left: 50%;
        top: 100%;
        transform: translate(-50%, -50%);
    }
</style>