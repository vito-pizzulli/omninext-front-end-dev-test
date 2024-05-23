<template>
    <div id="header-navbar">
        <nav class="desktop">
            <ul>
                <img src="/src/assets/logo.png" alt="MySarma Logo">
                <li v-for="(headerElement, index) in headerElements" :key="index"><a :href="headerElement.link">{{ headerElement.label }}</a></li>
                <li><a href="/login"><img src="/src/assets/icon-exit.png" alt="Access icon">Accedi alla piattaforma</a></li>
            </ul>
        </nav>

        <nav class="mobile">
            <ul>
                <li><img src="/src/assets/logo.png" alt="MySarma Logo"></li>
                <li><a href="/login"><img src="/src/assets/icon-exit.png" alt="Access icon">Accedi</a></li>
                <li><img src="/src/assets/icon-hamburger.png" alt="Hamburger icon"></li>
            </ul>
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

        nav {
            ul {
                @include flex(row, space-between, center, wrap);
                padding: 1rem;
            }

            &.mobile ul li:first-of-type {
                width: 50%;
            }
        }
    }
</style>