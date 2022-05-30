<template>
    <div class="single-champion container">
      <pre>{{ champion }}</pre>      
        <div class="champion-info">
          <div class="champion-img">
            <img :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/splash/${champion.id}_0.jpg`" alt="">
          </div>
        </div>
        <div class="champion-content">
          <h1>Nome: {{ champion.name }}</h1>
          <p class="champion-fact title">
            <span>Titolo: </span> "{{ champion.title }}"
          </p>
        </div>

    </div>
</template>

<script>
export default {
    async asyncData({ params, $axios }) {
        const json = await $axios.$get(
            `https://ddragon.leagueoflegends.com/cdn/12.9.1/data/it_IT/champion/${params.id}.json`
            )
        const champion = json.data
        return { champion }
    },
}
</script>

<style lang="scss" scoped>
.single-champion {
  color: #fff;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 32px 16px;
  .button {
    align-self: flex-start;
    margin-bottom: 32px;
  }
  .champion-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 32px;
    color: #fff;
    @media (min-width: 800px) {
      flex-direction: row;
      align-items: flex-start;
    }
    .champion-img {
      img {
        max-height: 500px;
        width: 100%;
        @media (min-width: 800px) {
          max-height: 700px;
          width: initial;
        }
      }
    }
    .champion-content {
      h1 {
        font-size: 56px;
        font-weight: 400;
      }
      .champion-fact {
        margin-top: 12px;
        font-size: 20px;
        line-height: 1.5;
        span {
          font-weight: 600;
          text-decoration: underline;
        }
      }
      .title {
        font-style: italic;
        span {
          font-style: normal;
        }
      }
    }
  }
}
</style>