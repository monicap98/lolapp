<template>
    <div class="champion-hero">
        <img
            :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/splash/${champion.id}_0.jpg`"
            alt=""
        />

        <div class="text-container">
            <div class="text">
                <span class="mini-heading">League of Legends</span>
                <h1><span>Scegli un </span>CAMPIONE</h1>
                <p class="paragraph">Con più di 140 campioni, troverai quello perfetto per il tuo stile di gioco.<br>Padroneggiane uno, o tutti.</p> <br>
                <a href="#champion-grid" class="button">Vedi campioni</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'championHero',
}
</script>

<style lang="scss" scoped>

</style>