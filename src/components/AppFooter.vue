<template>
    <div id="app-footer">
        <footer>
            <div class="container">
                <div class="upper-section">
                    <div class="logo-section">
                        <img class="logo" src="/src/assets/logo-footer.svg" alt="MySarma Logo">
                        <img class="flag" src="/src/assets/italian-flag-row.svg" alt="Italian flag row">
                        <p class="small">Il welfare aziendale tutto italiano a portata di PMI.</p>
                    </div>
                    <div class="footer-column" v-for="(footerElement, index) in footerElements" :key="index">
                        <p class="bold">{{ footerElement.name }}</p>
                        <ul>
                            <li v-for="(item, index) in footerElement.items" :key="index">
                                <p v-if="!item.iconUrl"><a :href="item.link">{{ item.label }}</a></p>
                                <p class="icon-link" v-if="item.iconUrl"><img class="icon" v-if="item.iconUrl" :src="item.iconUrl" :alt="item.label"> <a :href="item.link">{{ item.label }}</a></p>
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="bottom-section">
                    <p class="small">Copyright <i class="fa-regular fa-copyright"></i> MySarma srl - Tutti i diritti riservati</p>
                    <p class="small bold">Privacy e Cookie Policy</p>
                </div>
            </div>
        </footer>
    </div>
</template>

<script>
    import { footerElements } from '/data/data.json';

    export default {
        name: 'AppFooter',

        data () {
            return {
                footerElements: footerElements,
            }
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    footer {
        background-color: map-get(map-get($colors, Black), 600);
        color: map-get(map-get($colors, Black), 50);

        div.upper-section {
            @include flex(row, space-around, start, wrap);
            padding: 5rem 1rem 3rem;

            div.logo-section {
                text-align: center;
                @include flex(column, center, center, wrap);
                margin-bottom: 4rem;

                img.logo,
                img.flag {
                    display: block;
                    margin-bottom: 1rem;
                }
            }

            div.footer-column {
                p {
                    width: 100%;
                    margin-bottom: .5rem;
                }

                li {
                    margin-bottom: .5rem;

                    a {
                        color: grey;
                    }
                }

                img.icon {
                    width: 25px;
                }

                &:last-of-type {
                    border-left: 1px solid grey;
                    padding-left: 3rem;
                    margin-bottom: 0;

                    @media screen and (max-width: 767px) {
                        border-left: none;
                        padding-left: 0;
                    }

                    a {
                        font-weight: 700;
                        color: map-get(map-get($colors, Primary), 200);
                    }

                    li:last-of-type {
                        margin-top: 3rem;

                        a {
                            color: map-get(map-get($colors, Black), 200);
                        }
                    }
                }

                @media screen and (max-width: 767px) {
                    width: 50%;
                    margin-bottom: 3rem;

                    &:first-of-type {
                        width: 100%;
                    }
                }
            }

            p {
                width: 50%;

                &.icon-link {
                    @include flex(row, center, center, wrap);
                    gap: .8rem;

                    @media screen and (max-width: 767px) {
                        justify-content: start;
                    }
                }
            }
        }

        div.bottom-section {
            @include flex(row, space-between, center, wrap);
            color: grey;
            border-top: 1px solid grey;
            padding: 1rem;

            @media screen and (max-width: 767px) {
                p {
                    margin-bottom: .5rem;
                }
            }
        }
    }
</style>