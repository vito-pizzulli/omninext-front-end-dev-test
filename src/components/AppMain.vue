<template>
    <div id="app-main">
        <main>
            <PrimaryContent />
            <MobileApp />
        </main>
    </div>
</template>

<script>
    import PrimaryContent from './PrimaryContent.vue';
    import MobileApp from './MobileApp.vue';

    export default {
        name: 'AppMain',

        components: {
            PrimaryContent,
            MobileApp
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;
</style>