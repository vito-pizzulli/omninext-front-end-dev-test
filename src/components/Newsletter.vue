<template>
    <div id="newsletter">
        <div class="container">
            <div class="left-side">
                <div>
                    <h2 class="desktop">Resta aggiornato</h2>
                    <h3 class="mobile">Resta aggiornato</h3>
                    <p>Iscriviti alla newsletter per ricevere aggiornamenti sulle nuove offerte e partner MySarma</p>
                </div>    
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
        padding: 10rem 1.5rem;

        @media screen and (max-width: 767px) {
            padding: 6rem 1.5rem;
        }

        div.container {
            @include flex(row, center, center, no-wrap);
            gap: 8rem;

            @media screen and (max-width: 767px) {
                flex-direction: column;
                gap: 3rem;
            }

            div.left-side {
                width: 27%;

                @media screen and (max-width: 767px) {
                    width: 100%;
                }

                h2,
                h3 {
                    margin-bottom: 1rem;
                }
            }

            div.right-side {
                width: 40%;
                text-align: end;

                @media screen and (max-width: 767px) {
                    width: 100%;
                }

                p {
                    margin-bottom: 1rem;
                    text-align: start;
                }

                input {
                    margin-right: 4rem;
                    width: 60%;

                    @media screen and (max-width: 767px) {
                        width: 100%;
                        margin-bottom: 2rem;
                    }
                }

                button {
                    display: inline-block;
                    border-radius: 10px;
                    padding: .8rem 2rem;
                }
            }
        }
    }
</style>