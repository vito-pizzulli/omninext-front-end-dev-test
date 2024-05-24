<template>
    <div id="app-main">
        <main>
            <PrimaryContent />
            <MobileApp />
            <CorporateWelfare />
            <CollaboratorsWellness />
            <AvailablePlans />
            <Newsletter />
        </main>
    </div>
</template>

<script>
    import PrimaryContent from './PrimaryContent.vue';
    import MobileApp from './MobileApp.vue';
    import CorporateWelfare from './CorporateWelfare.vue';
    import CollaboratorsWellness from './CollaboratorsWellness.vue';
    import AvailablePlans from './AvailablePlans.vue';
    import Newsletter from './Newsletter.vue';

    export default {
        name: 'AppMain',

        components: {
            PrimaryContent,
            MobileApp,
            CorporateWelfare,
            CollaboratorsWellness,
            AvailablePlans,
            Newsletter
        }
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;
</style>