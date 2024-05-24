<template>
    <div id="app-footer">
        <footer>
            <div class="upper-section">
                <div class="logo-section">
                    <img src="/src/assets/logo-footer.png" alt="MySarma Logo">
                    <img src="/src/assets/italian-flag-row.png" alt="Italian flag row">
                    <p class="small">Il welfare aziendale tutto italiano a portata di PMI.</p>
                </div>
                <div class="footer-column" v-for="(footerElement, index) in footerElements" :key="index">
                    <p class="bold">{{ footerElement.name }}</p>
                    <ul>
                        <li v-for="(item, index) in footerElement.items" :key="index">
                            <a :href="item.link">{{ item.label }}</a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="bottom-section">
                <p>Copyright <i class="fa-regular fa-copyright"></i> MySarma srl - Tutti i diritti riservati</p>
                <p>Privacy e Cookie Policy</p>
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
            @include flex(row, space-around, center, wrap);

            div.footer-column {
                &:last-of-type {
                    border-left: 1px solid map-get(map-get($colors, Black), 200);
                    padding-left: 1rem;

                    li:last-of-type {
                        margin-top: 3rem;
                    }
                }

                @media screen and (max-width: 767px) {
                    width: 50%;

                    &:first-of-type {
                        width: 100%;
                    }
                }
            }

            img {
                display: block;
            }
        }

        div.bottom-section {
            @include flex(row, space-between, center, wrap);
            color: map-get(map-get($colors, Black), 200);
            border-top: 1px solid map-get(map-get($colors, Black), 200);
        }
    }
</style>