<template>
    <div id="header-navbar">
        <nav class="desktop">
            <ul>
                <img src="/src/assets/logo.png" alt="MySarma Logo">
                <li v-for="(headerElement, index) in headerElements" :key="index"><a :href="headerElement.link"></a>{{ headerElement.label }}</li>
                <li><img src="/src/assets/icon-exit.png" alt="">Accedi alla piattaforma</li>
            </ul>
        </nav>

        <nav class="mobile">
            <img src="/src/assets/logo.png" alt="MySarma Logo">
        </nav>
    </div>
</template>

<script>
    import { headerElements } from '/data/data.json';

    export default {
        name: 'HeaderNavbar',

        data() {
            return {
                headerElements: headerElements
            }
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div#header-navbar {
        width: 85%;
        margin: auto;
    }

    ul {
        @include flex(row, space-between, center, wrap);
        padding: 1rem;
    }
</style>