<template>
    <div class="welfare-card">
        <img :src="imgUrl" :alt="label">
        <p class="bold">{{ label }}</p>
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
        
    }
</style>