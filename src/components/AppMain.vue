<template>
    <div id="app-main">
        <main>
            <PrimaryContent />
        </main>
    </div>
</template>

<script>
    import PrimaryContent from './PrimaryContent.vue';

    export default {
        name: 'AppMain',

        components: {
            PrimaryContent
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;
</style>