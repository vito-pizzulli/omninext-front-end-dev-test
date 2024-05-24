<template>
    <div id="app-main">
        <main>
            <PrimaryContent />
            <MobileApp />
            <CorporateWelfare />
            <CollaboratorsWellness />
            <AvailablePlans />
        </main>
    </div>
</template>

<script>
    import PrimaryContent from './PrimaryContent.vue';
    import MobileApp from './MobileApp.vue';
    import CorporateWelfare from './CorporateWelfare.vue';
    import CollaboratorsWellness from './CollaboratorsWellness.vue';
    import AvailablePlans from './AvailablePlans.vue';

    export default {
        name: 'AppMain',

        components: {
            PrimaryContent,
            MobileApp,
            CorporateWelfare,
            CollaboratorsWellness,
            AvailablePlans
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;
</style>