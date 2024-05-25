<template>
    <div id="header-navbar">
        <div class="container">
            <nav class="desktop">
                <ul>
                    <li><img class="logo" src="/src/assets/logo-header.svg" alt="MySarma Logo"></li>
                    <li v-for="(headerElement, index) in headerElements" :key="index"><a class="bold" :href="headerElement.link">{{ headerElement.label }}</a></li>
                    <li><button class="login"><img src="/src/assets/icon-exit.svg" alt="Access icon">Accedi alla piattaforma</button></li>
                </ul>
            </nav>

            <nav class="mobile">
                <ul>
                    <li><img class="logo" src="/src/assets/logo-header.svg" alt="MySarma Logo"></li>
                    <li><button class="login"><img src="/src/assets/icon-exit.svg" alt="Access icon">Accedi</button></li>
                    <li><button><img src="/src/assets/icon-hamburger.svg" alt="Hamburger icon"></button></li>
                </ul>
            </nav>
        </div>
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
        nav {
            ul {
                @include flex(row, space-between, center, no-wrap);
                padding: 1rem 0;

                li {
                    button.login {
                        background-color: map-get(map-get($colors, Green), 200);
                        transition: all .3s ease;

                        &:hover {
                            background-color: map-get(map-get($colors, Green), 500);;
                        }

                        img {
                            margin-right: .5rem;
                        }
                    }

                    &:first-of-type {
                        width: 20%;
                    }
                }

                a {
                    color: map-get(map-get($colors, Primary), 500);
                }
            }

            &.mobile {
                padding: 0 .8rem;

                img.logo {
                    width: 150px;
                    margin-right: 2rem;
                }

                button.login {
                    background-color: white;
                    color: map-get(map-get($colors, Green), 600);
                    font-size: 1.2rem;

                    img {
                        filter: brightness(200%);
                        width: 25px;
                    }
                }

                ul li:first-of-type {
                    width: 50%;
                }
            }
        }

        @media screen and (max-width: 767px) {
            width: 100%;
        }
    }
</style>