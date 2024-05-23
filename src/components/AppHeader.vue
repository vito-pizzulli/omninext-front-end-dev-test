<template>
    <div id="app-header">
        <header>
            <HeaderNavbar />
        </header>
    </div>
</template>

<script>
import HeaderNavbar from './HeaderNavbar.vue';

export default {
    name: 'AppHeader',

    components: {
        HeaderNavbar
    }
}
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;
</style>