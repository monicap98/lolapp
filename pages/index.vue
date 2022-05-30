<template>
  <div class="home">
    <!-- Hero -->
    <Hero />

    <!-- Heading -->
    <div class="section">
      <div class="general-wrapper">
        <div class="heading-wrapper">
          <h1 class="heading">
            <span class="intro">
              <div class="reveal-wrapper">
                <span>scegli un</span>
              </div>
            </span>
            <strong class="big-title">
              <div class="reveal-wrapper">
                <span class="big-big-title">campione</span>
              </div>
            </strong>
          </h1>
        </div>
        <p class="description">
          Con più di 140 campioni, troverai quello perfetto per il tuo stile di gioco. Padroneggiane uno, o tutti.
        </p>

        <div class="body">

          <!-- Filters -->
          <Filters />

    <!-- Champions -->

    <div class="container champions">
      <div id="champion-grid" class="champions-grid">
          <div class="champion" v-for="champion in champions" :key="champion.id">
          <div class="champion-img">
            <img
              :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/loading/${champion.id}_0.jpg`"
              alt=""
            />
            <p class="difficulty">{{champion.info.difficulty}}</p>
            <p class="blurb">{{champion.blurb}}</p>
          </div>
            <div class="info">
              <p class="title">{{champion.name}}</p>
              <p class="subtitle">{{champion.title}}</p>
              <NuxtLink
                :to="{ name: 'champions-championid', params: { id : champion.id }}"
                class="button button-light">
                Scopri di più
              </NuxtLink>
            </div>
          </div>
       </div> 
      </div>
    </div>
  </div>
        </div>
      </div>

</template>

<script>
export default {
  data() {
    return {
      searchedChampions: [],
      searchInput: '',
    }
  },
  async asyncData({ params, $axios }) {
    const json = await $axios.$get(
      'https://ddragon.leagueoflegends.com/cdn/12.9.1/data/it_IT/champion.json'
    )
    const champions = json.data
    return { champions }
  },
  methods: {
    async searchedChampions () {
      const data = axios.get()
    }
  },
}
</script>

<style lang="scss" scoped>

.section {
  margin-top: -150px;
}
.general-wrapper {
  padding: 100px 0px 140px;
}

// Heading
.heading-wrapper {
  position: relative;
  z-index: 1;
  text-align: center;
  color: white;
}
.heading {
  margin: 0px;
  font-weight: normal;
}
.intro {
    text-transform: uppercase;
    font-style: italic;
    line-height: 1.1;
    display: block;
    font-size: 1.5rem;
    line-height: 1;
    font-weight: 600;
    letter-spacing: 0.1em;
}
.reveal-wrapper {
  display: inline-block;
  clip-path: polygon(100% 100%, -200% 100%, 100% -200%);
  animation-duration: 2800ms;
  animation-delay: 300ms;
  animation-timing-function: cubic-bezier(0.165, 0.84, 0.44, 1);
}
.big-title {
  text-transform: uppercase;
  font-style: italic;
  line-height: 1.1;
  display: block;
  font-size: 120px;
  line-height: 0.85;
  font-family: "Beaufort for LOL", serif;
  font-weight: 800;
  letter-spacing: 0.03em;
  @media (min-width: 600px) {
    font-size: calc(43.27px + 2.12vw);
  }
}
.big-big-title {
  display: block;
  padding: 0px 15px 10px;
  margin-bottom: -10px;
}
.description {
  display: block;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  line-height: 1.6;
  max-width: 460px;
  padding: 0px 10%;
  margin: 12px auto 0px;
  font-size: 0.875rem;
  text-align: center;
  letter-spacing: 0.08em;
  line-height: 1.6;
  animation: 1000ms cubic-bezier(0.215, 0.61, 0.355, 1) 400ms 1 normal both running;
}

.body {
  margin-top: 75px;
}

 .button {
   border-top-left-radius: 0;
   border-bottom-left-radius: 0;
 }


  .champions {
    padding: 32px 16px;
    .champions-grid {
      display: grid;
      column-gap: 32px;
      row-gap: 64px;
      grid-template-columns: 1fr;
      @media (min-width: 500px) {
        grid-template-columns: repeat(2, 1fr);
      }
      @media (min-width: 750px) {
        grid-template-columns: repeat(2, 1fr);
      }
      @media (min-width: 1100px) {
        grid-template-columns: repeat(4, 1fr);
      }
      .champion {
        position: relative;
        display: flex;
        flex-direction: column;
        .champion-img {
          position: relative;
          overflow: hidden;
          &:hover {
            .blurb {
              transform: translateY(0);
            }
          }
          img {
            display: block;
            width: 100%;
            height: 100%;
          }
          .difficulty {
            position: absolute;
            top: 0;
            left: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            width: 40px;
            height: 40px;
            background-color: #d0a85c;
            color: #fff;
            border-radius: 0 0 16px 0;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
              0 2px 4px -1px rgba(0, 0, 0, 0.06);
          }
          .blurb {
            line-height: 1.5;
            position: absolute;
            bottom: 0;
            background-color: #d0a85c;
            padding: 12px;
            color: #fff;
            transform: translateY(100%);
            transition: 0.3s ease-in-out all;
          }
        }
        .info {
          margin-top: auto;
          .title {
            margin-top: 8px;
            color: #fff;
            font-size: 20px;
          }
          .subtitle {
            margin-top: 8px;
            color: #c9c9c9;
          }
          .button {
            margin-top: 8px;
          }
        }
      }
    }
  }
</style>