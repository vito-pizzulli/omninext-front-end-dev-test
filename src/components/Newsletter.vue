<template>
    <div id="newsletter">
        <div class="container">
            <div class="left-side">
                <h2>Resta aggiornato</h2>
                <p>Iscriviti alla newsletter per ricevere aggiornamenti sulle nuove offerte e partner MySarma</p>
            </div>
            <div class="right-side">
                <p class="bold">Il tuo indirizzo email</p>
                <input type="text">
                <button>Invia</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Newsletter'
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div#newsletter {
        background-image: url("/src/assets/newsletter-pattern.png");
        color: map-get(map-get($colors, Black), 50);

        div.container {
            @include flex(row, center, center, no-wrap);

            @media screen and (max-width: 767px) {
                flex-direction: column;
            }
        }
    }
</style>