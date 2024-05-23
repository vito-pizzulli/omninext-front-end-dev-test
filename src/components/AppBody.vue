<template>
    <div id="app-body">
        <AppHeader />
        <AppMain />
        <AppFooter />
    </div>
</template>

<script>
import AppHeader from './AppHeader.vue';
import AppMain from './AppMain.vue';
import AppFooter from './AppFooter.vue';

export default {
    name: 'AppBody',

    components: {
        AppHeader,
        AppMain,
        AppFooter
    }
}
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;
</style>