<template>
  <div class="home">
    <!-- Heading -->
        <div class="heading-wrapper">
          <h1 class="heading">
            <span class="intro">
                <span>scegli un</span>
            </span>
            <strong class="big-title">
                <span class="big-big-title">campione</span>
            </strong>
          </h1>
        </div>
        <p class="description">
          Con più di 140 campioni, troverai quello perfetto per il tuo stile di gioco. Padroneggiane uno, o tutti.
        </p>

        <div class="body">

          <!-- Filters
          <Filters />
          -->

    <!-- Champions -->
    <div class="background"></div>
    <div class="container champions">
      <div id="champion-grid" class="champions-grid">
          <div class="champion" v-for="champion in champions" :key="champion.id">
          <NuxtLink :to="{ name: 'champions-championid', params: { id : champion.id }}" class="champion-img">
            <img
              :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/loading/${champion.id}_0.jpg`"
              alt=""
            />
            <div class="info2">
              <h1 class="title2">{{champion.name}}</h1>
              <h2 class="subtitle2">
                <span>{{champion.title}}</span>
                </h2>
            </div>
            <div class="action">
              <span>Esplora</span>
              <span class="arrow" style="width: 25px; height: 12.5px">
                <span class="hover-arrow">
                  <svg version="1.0" x="0px" y="0px" viewBox="0 0 162 70.28" fill="#c4b998" style="width: 12.5px;">
                    <circle fill="#c4b998" cx="31.57" cy="35.21" r="11.57"></circle>
                    <g>
                      <polygon fill="#c4b998" points="124.18,70.39 118.31,64.09 149.37,35.22 118.31,6.35 124.18,0.05 162,35.22"></polygon>
                      <rect x="84.61" y="29.76" fill="#c4b998" width="65" height="11.06"></rect>
                    </g>
                  </svg>
                </span>
                <span class="rest-arrow">
                  <svg version="1.0" x="0px" y="0px" viewBox="0 0 162 70.28" fill="#937341" style="width: 12.5px;">
                    <circle fill="#937341" cx="31.57" cy="35.21" r="11.57"></circle>
                    <g>
                      <polygon fill="#937341" points="124.18,70.39 118.31,64.09 149.37,35.22 118.31,6.35 124.18,0.05 162,35.22"></polygon>
                      <rect x="84.61" y="29.76" fill="#937341" width="65" height="11.06"></rect>
                    </g>
                  </svg>
                </span>
              </span>
            </div>
            </NuxtLink>
          </div>
       </div> 
      </div>
    </div>
  </div>

</template>

<script>
export default {
  async asyncData({ params, $axios }) {
    const json = await $axios.$get(
      'https://ddragon.leagueoflegends.com/cdn/12.9.1/data/it_IT/champion.json'
    )
    const champions = json.data
    return { champions }
  },
}
</script>

<style lang="scss" scoped>
.home {
  padding-top: 120px;
  align-items: flex-start;
  @media (max-width: 500px) {
    padding-top: 64px;
  }
}
.background {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  filter: brightness(.4);
  background-image: url(../assets/imgs/championsBackground.jpg);
  background-position: top;
  background-repeat: no-repeat;
  background-size: contain;
  opacity: .2;
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
    @media (max-width: 599px) {
    font-size: 1rem;
  }
}
.big-title {
  text-transform: uppercase;
  font-style: italic;
  line-height: 1.1;
  display: block;
  font-size: 120px;
  line-height: 0.85;
  font-family: BeaufortforLOL-Bold, sans-serif;
  font-weight: 800;
  letter-spacing: 0.03em;
  @media (max-width: 599px) {
    font-size: calc(22.24px + 4.3vw);
  }
  @media (min-width: 320px) {
    font-size: calc(22.24px + 4.3vw);
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
  margin-top: 48px;
}

  .champions {
    padding: 32px 80px;
    @media (max-width: 500px) {
    margin: calc(1.3%) calc(0.8%) 0px;
    padding: 0px 3.2% 0px 3.2%;
    }
    .champions-grid {
      display: grid;
      column-gap: 16px;
      row-gap: 32px;
      grid-template-columns: 1fr;
      @media (max-width: 500px) {
        grid-template-columns: repeat(2, 1fr);
        row-gap: 0px;
      }
      @media (min-width: 750px) {
        grid-template-columns: repeat(2, 1fr);
      }
      @media (min-width: 1100px) {
        grid-template-columns: repeat(5, 1fr);
      }
      .champion {
        position: relative;
        display: flex;
        flex-direction: column;
        flex: 0 1 19%;
        height: 425px;
        margin-bottom: 1%;
        margin-right: 1%;
        opacity: 1;
        @media (max-width: 500px) {
          padding-bottom: 2px;
          padding-right: 2px;
        }
      }
        .champion-img {
          position: relative;
          overflow: hidden;
          transition-property: transform,z-index,border;
          transition-timing-function: ease,linear,ease;
          transition-duration: .4s,.4s,.4s;
          border: 1px solid rgba(10,10,12,.9);
          box-shadow: 0 0 16px 14px rgb(0 0 0 / 20%);
          z-index: 1;
          &:hover {
            @media (min-width: 768px) {
              transition-timing-function: ease, step-start, ease;
              transform: scale(1.05);
              border: 1px solid #927345;
              z-index: 3;
            }
          }
          &:hover .info2 {
            @media (min-width: 768px) {
              bottom: 54px;
            }
          }        
          &:hover .action {
            @media (min-width: 768px) {
              background-color: rgba(10,10,12,.94);
              border-top: 1px solid #927345;
              height: 54px;
            }
          }
          img {
            display: block;
            width: 110%;
            height: 110%;
            object-fit: cover;
            object-position: -10px -10px;
          }
        }
        .info2 {
          position: absolute;
          right: 0;
          bottom: 0;
          left: 0;
          background-color: rgba(10,10,12,.9);
          border-top: 1px solid #927345;
          padding: 22px;
          text-align: center;
          transition: .4s;
        }
        .title2 {
          color: #937341;
          font-size: 14px;
          letter-spacing: 2px;
          font-family: BeaufortforLOL-Bold, sans-serif;
          font-weight: 500;
          text-transform: uppercase;
        }
        .subtitle2 {
          color: #c4b998;
          font-size: 12px;
          letter-spacing: .05em;
          padding-top: 6px;
          font-family: BeaufortforLOL-Bold, sans-serif;
          font-weight: 500;
          text-transform: capitalize;
        }
        .action {
          position: absolute;
          right: 0;
          bottom: 0;
          left: 0;
          font-family: BeaufortforLOL-Bold, sans-serif;
          font-weight: 700;
          font-size: 11px;
          background-color: rgba(10,10,12,.9);
          border-top: 1px solid rgba(10,10,12,.9);
          color: #937341;
          height: 0;
          letter-spacing: .3em;
          line-height: 54px;
          overflow: hidden;
          text-align: center;
          text-decoration: none;
          text-transform: uppercase;
          transition: .4s;
          &:hover .arrow .hover-arrow {
            transform: translateX(50%);
            transition-delay: .22s;
            opacity: 1;
          }
          &:hover .arrow .rest-arrow {
            transform: translateX(230%);
            transition-delay: 0s;
            opacity: 0;
          }
        }
        .arrow {
          position: relative;
          display: inline-block;
          cursor: pointer;
          line-height: 1;
          top: 2px;
        }
        .hover-arrow {
          transition: .44s;
          opacity: 0;
          position: absolute;
          top: 0;
          left: 0;
          transform: translateX(-130%);
        }
        .hover-arrow svg, .rest-arrow svg {
          max-height: 25px;
        }
        .rest-arrow {
          transition: .44s;
          position: absolute;
          top: 0;
          left: 0;
          transition-delay: .22s;
          opacity: 1;
          transform: translateX(50%);
        }
        }
      }
</style>