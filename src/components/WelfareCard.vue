<template>
    <div class="welfare-card">
        <img :src="imgUrl" :alt="label">
        <p class="desktop bold">{{ label }}</p>
        <p class="mobile big bold">{{ label }}</p>
        <p>{{ text }}</p>
        <button>Scopri di più</button>
    </div>
</template>

<script>
    export default {
        name: 'WelfareCard',

        props: {
            label: String,
            text: String,
            imgUrl: String,
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div.welfare-card {
        @include flex(column, space-between, center, wrap);

        img {
            max-height: 100px;
            margin-bottom: .8rem;

            @media screen and (max-width: 767px) {
                margin-bottom: 4rem;
            }
        }

        p {
            color: #6d7791;
            width: 80%;
            margin-bottom: 1rem;

            &.big {
                margin-bottom: .5rem;
            }
        }

        button {
            background-color: #f6f9ff;
            font-weight: 400;

            @media screen and (max-width: 767px) {
                margin-bottom: 4rem;
            }
        }
    }
</style>