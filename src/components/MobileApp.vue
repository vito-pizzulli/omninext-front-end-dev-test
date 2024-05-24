<template>
    <div id="mobile-app">
        <div class="desktop">
            <div class="container">
                <div class="left-side">
                    <h1>App</h1>
                    <p class="big grey">Con l'app MySarma gestirai il tuo credito welfare e potrai accedere al catalogo dei Benefit e Servizi acquistabili.</p>
                    <p><i class="fa-solid fa-arrow-right"></i> COMING SOON</p>
                </div>
                <div class="right-side">
                    <img src="/src/assets/app.svg" alt="App view image">
                </div>
            </div>
        </div>

        <div class="mobile">
            <h2>App</h2>
            <img src="/src/assets/app.svg" alt="App view image">
            <p class="big grey">Con l'app MySarma gestirai il tuo credito welfare e potrai accedere al catalogo dei Benefit e Servizi acquistabili.</p>
            <p><i class="fa-solid fa-arrow-right"></i> COMING SOON</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'MobileApp'
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div#mobile-app {
        @include flex(row, center, center, wrap);
        margin: 8rem 1rem;

        div.desktop div.container {
            @include flex(row, center, center, wrap);

            div.left-side {
                width: 50%;

                h1 {
                    margin-bottom: 4rem;
                    color: map-get(map-get($colors, Primary), 700);
                }

                p {
                    width: 70%;
                    margin-bottom: 7rem;

                    &.grey {
                        color: grey;
                    }
                }

                i {
                    margin-right: 1rem;
                }
            }

            div.right-side {
                text-align: center;
                width: 50%;
            }
        }

        div.mobile {
            margin-top: 11rem;
            padding: 0 1rem;

            h2 {
                margin-bottom: 4rem;
                color: map-get(map-get($colors, Primary), 700);
            }

            img {
                width: 100%;
                margin-bottom: 4rem;
            }

            p {
                    margin-bottom: 3rem;

                    &.grey {
                        color: grey;
                    }
                }

                i {
                    margin-right: 1rem;
                }
        }
    }
</style>