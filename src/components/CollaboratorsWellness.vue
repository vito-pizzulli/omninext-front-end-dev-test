<template>
    <div id="collaborators-wellness">
        <p class="big">Sfrutta al meglio il tuo potenziale e fai crescere</p>
        <h4>il benessere dei tuoi collaboratori</h4>
        <p>Attiva subito un <strong>Piano Go</strong> oppure richiedi un preventivo gratuito per attivare un <strong>Piano Pro</strong>. Il nostro Welfare guru è pronto a consigliarti la migliore soluzione in base alle tue esigenze.</p>
    </div>
</template>

<script>
    export default {
        name: 'CollaboratorsWellness',
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    div#collaborators-wellness {
        background-image: url("/src/assets/go-plan-pattern.png");
        background-color: map-get(map-get($colors, Primary), 700);
        color: map-get(map-get($colors, Black), 50);
        text-align: center;
    }
</style>