<template>
    <div id="mobile-app">
        <div class="desktop">
            <div class="container">
                <div class="left-side">
                    <h1>App</h1>
                    <p class="big">Con l'app MySarma gestirai il tuo credito welfare e potrai accedere al catalogo dei Benefit e Servizi acquistabili.</p>
                    <p><i class="fa-solid fa-arrow-right"></i> COMING SOON</p>
                </div>
                <div class="right-side">
                    <img src="/src/assets/app.png" alt="App view image">
                </div>
            </div>
        </div>

        <div class="mobile">
            <h2>App</h2>
            <img src="/src/assets/app.png" alt="App view image">
            <p class="big">Con l'app MySarma gestirai il tuo credito welfare e potrai accedere al catalogo dei Benefit e Servizi acquistabili.</p>
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
        padding: 1rem;

        div.desktop div.container {
            @include flex(row, center, center, wrap);

            div.left-side {
                width: 60%;
            }

            div.right-side {
                width: 40%;
            }
        }

        div.mobile {
            padding-top: 15rem;

            img {
                max-width: 80%;
            }
        }
    }
</style>