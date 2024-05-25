<template>
    <div id="dropdown-menu">
        <nav>
            <ul>
                <li v-for="(headerElement, index) in headerElements" :key="index">
                    <a class="bold" :href="headerElement.link">{{ headerElement.label }}</a>
                    <hr>
                </li>
                <li><button class="login"><img src="/src/assets/icon-exit.svg" alt="Access icon">Accedi alla piattaforma</button></li>
            </ul>
        </nav>
    </div>
</template>

<script>
    import { headerElements } from '/data/data.json';

export default {
    name: 'DropdownMenu',

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

    div#dropdown-menu {
        padding: 1rem;
        position: absolute;
        z-index: 1;
        background-color: white;
        left: 0;
        width: 100%;

        nav ul {
            padding: 1rem;
            width: 80%;
            margin: auto;

            li {
                margin-bottom: 1rem;

                a {
                    color: map-get(map-get($colors, Primary), 500);
                }

                hr {
                    margin-top: 1rem;
                    border-top: 1px solid map-get(map-get($colors, Primary), 200);
                    border-left: none;
                    border-right: none;
                    border-bottom: none;
                }

                button.login {
                    background-color: map-get(map-get($colors, Green), 200);
                    transition: all .3s ease;
                    margin: auto;
                    margin-top: 2rem;

                    &:hover {
                        background-color: map-get(map-get($colors, Green), 500);
                    }

                    img {
                        margin-right: .5rem;
                    }
                }
            }
        }
    }
</style>