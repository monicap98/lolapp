<template>
    <div class="hero">
        <img src="../assets/imgs/lol.jpg" alt="" />
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
    name: 'Hero',
}
</script>

<style lang="scss" scoped>
.hero {
  height: 400px;
  position: relative;
  @media (min-width: 750px) {
    height: 500px;
  }
  &::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.6);
  }
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .text-container {
    z-index: 99;
    position: absolute;
    top: 0;
    margin: 0;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    .text {
      padding: 0 16px;
      width: 100%;
      max-width: 1400px;
      margin: 0 auto;
    }
    .mini-heading {
      font-weight: 600;
      font-size: 18px;
      text-transform: uppercase;
      color: #d0a85c;
      margin-bottom: 8px;
      @media (min-width: 750px) {
        font-size: 22px;
      }
    }
    h1 {
      color: #fff;
      font-size: 64px;
      font-weight: 200;
      margin-bottom: 8px;
      @media (min-width: 750px) {
        font-size: 84px;
      }
      span {
        font-weight: 500;
      }
    }
    .paragraph {
        font-family: 'Spiegel';
        color:#fff;
    }
    .button {
      font-size: 20px;
      align-self: flex-start;
    }
  }
}
</style>