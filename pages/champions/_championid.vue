<template>
  <div class="general">  
    <section class="wrapper">
      <div class="background-asset">   
        <div class="background-img">
          <img :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/splash/${champion.id}_0.jpg`" alt="" class="blurimg">
          <img :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/splash/${champion.id}_0.jpg`" alt="" class="clearimg">
        </div>
      </div>
      <div class="intro-wrapper">
        <div class="left-title">
          <div class="left-text-container">
            <div class="left-text">Panoramica</div>
          </div>
        </div>
        <div class="right-content"></div>
      </div>
      <div class="section-inner">
        <div class="dock">
          <div class="name-container">
            <div class="name-wrapper">
              <h1 class="heading">
                <span class="intro">
                  <div class="reveal-wrapper">
                    <span>{{ champion.title }}</span>
                  </div>
                </span>
                <strong class="intro-name">
                  <div class="reveal-wrapper">
                    <span class="champ-name">{{ champion.name }}</span>
                  </div>
                </strong>
              </h1>
            </div>
          </div>
          <img class="divider" src="../../assets/imgs/HeaderDivider.png" alt="Divider"></img>
          <div class="info-wrapper">
            <div class="specs">
              <ul class="specs-list">
                <li class="specs-item">
                  <div class="specs-item-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" class="specs-icon">
                      <path d="M67.84 56.35v5.5c8.62-8.62 14.37 0 14.37 0C112.14 40.78 90.35 2 90.35 2s-.72 17.24-15.08 27.77v16.52c-.24 4.79-3.84 7.9-7.43 10.06M17.79 62.09s4.07-6.46 10.78-2.63L20.91 48.2l6.7-16c-17.24-10.54-18-29.93-18-29.93S-12.14 41 17.79 62.09M26.89 83.89l5.51-18.68-.24-.48L19.23 77.9A17.78 17.78 0 017.5 83.17H3l-1 2.39 12 11.5zM92.27 83.89a16.24 16.24 0 01-11.74-5.27L68.8 66.88l3.83 17.72L85.8 98l12-11.49-1-2.4zM55.87 42.7c0 .24-.24.48-.24.71h.72c5.75.48 7.66 2.64 9.1 7.67a9.35 9.35 0 002.39-1.92c1-1 1.68-1.67 1.68-2.63V28.09a2 2 0 00-1.68-1.92l-31.37-5.74H36a2.39 2.39 0 00-2.39 2.39v6.71l24.9 3.35z"></path>
                      <path d="M60.18 54c-1.2-5.27-1.44-4.55-5.75-4.79L40.78 48v-3.87h5.51A4.09 4.09 0 0050.36 41l1-3.35L32.4 35l-5 12.22 11.74 17-5.54 18.47L49.88 98l16.53-15.07s-6.23-28.5-6.23-29M49.88 2.23l-4.79 10.29 4.79 3.83 4.79-3.83zM62.1 9.41l1.43 6h6l2.87-11zM30.25 15.4h6l.24-.72 1.2-5.27-10.3-5z"></path>
                    </svg>
                  </div>
                  <div class="specs-item-type">Ruolo</div>
                  <div class="specs-item-value">{{ champion.tags[0] }}</div>
                </li>
                <li class="specs-item">
                  <div class="specs-item-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" class="specs-icon">
                      <path d="M85.92 63.89L55 90V67.48h7.42v-9.1H37.55v9.1H45v22.75L14.08 63.89 8.33 21l27.54-10.51a39.13 39.13 0 0128.26 0L91.67 21zM66.28 5a47.61 47.61 0 00-32.56 0L2.11 17.19l6.7 49.57L41.86 95A13 13 0 0050 97.89 12.5 12.5 0 0058.14 95l33.05-28.24 6.7-49.57z"></path>
                      <path d="M78.74 32.28L62 21.26v5.27H38v-5.27l-16.26 7.19a2.9 2.9 0 00-1.67 3.11l4.31 19.16a3.22 3.22 0 002.15 2.15l11.26 2.4V50h23.94v5.27l11.5-2.4a2.52 2.52 0 002.15-2.15l4.31-15.57a2.39 2.39 0 00-1-2.87M57.42 20.07H42.58L50 11.68z"></path>
                    </svg>
                  </div>
                  <div class="specs-item-type">Difficoltà</div>
                  <div class="specs-item-value">{{ champion.info.difficulty }}</div>
                </li>
              </ul>
            </div>
            <div class="info-divider"></div>
            <div class="desc">
              <p class="p-desc">{{ champion.lore }}</p>
            </div>
          </div>
        </div>
        <div class="champions-button-container">
          <NuxtLink
                :to="{ name: 'index', params: { id : champion.id }}"
                class="champions-button-link">                
                <span class="champions-button-text">Lista campioni</span>
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 14 15" class="champions-button-icon">
                    <path d="M12.8 8.4V4.8S13 1.1 7 0h-.1c-6 1.1-5.8 4.8-5.8 4.8v3.6c0 1.9-.8 2.5-.8 2.5C1.5 15.3 4.5 15 4.5 15c-1.6-2.1 0-5.8 0-5.8-2.3-.3-1.9-2.7-1.7-3.4 0 0 2.2-.1 3.3 1.6v4.2l.9.9.8-.8V7.5c1.2-1.8 3.3-1.7 3.3-1.6.2.7.6 3.1-1.7 3.3 0 0 1.6 3.8 0 5.8 0 0 3 .3 4.2-4.1.1 0-.8-.6-.8-2.5z"></path>
                  </svg>
          </NuxtLink>
        </div>
      </div>
      <svg width="17" height="58" fill="none" xmlns="http://www.w3.org/2000/svg" class="scroll-indicator">
        <path d="M8.065 39.333l-5.02 5.02 5.02 5.021 5.02-5.02-5.02-5.02z"></path>
        <path d="M8.065 44.379L5.59 46.854l2.475 2.474 2.475-2.474-2.475-2.475z"></path>
        <path d="M4.6 47.8l-1.5 1.5 5 5 5-5-1.5-1.5M8.1 4.2v30"></path>
      </svg>
    </section>

    <section class="abilities">
      <h2 class="mobile-title">Abilità</h2>
      <div class="abilities-wrapper">
        <div class="left-title">
          <div class="left-text-container">
            <div class="left-text">Abilità</div>
          </div>
        </div>
        <div class="abilities-content">
          <div class="abilities-inner">
            <div class="selector-wrapper">
              <div class="wrapwrapper">
                <div class="wrapper-inner">
                  <div class="side-fill">
                    <div class="baseline-left"></div>
                  </div>
                  <div class="option-list" id="ability">
                    <h2 class="abilities-title">Abilità</h2>
                    <button @click='updateSpellInfos' data-spell-type="Passiva" :data-spell-name="champion.passive.name" :data-spell-desc="champion.passive.description"  class="option is-active">
                      <span class="option-icon">
                        <span class="option-icon-content">
                          <img :src="`http://ddragon.leagueoflegends.com/cdn/12.10.1/img/passive/${champion.passive.image.full}`" alt="">
                        </span>
                      </span>
                      <span class="option-line"></span>
                      <span class="option-bullet-container">
                        <span class="bullet"></span>
                      </span>
                    </button>
                    <button @click='updateSpellInfos' data-spell-type="Q" :data-spell-name="champion.spells[0].name" :data-spell-desc="champion.spells[0].description" class="option">
                      <span class="option-icon">
                        <span class="option-icon-content">
                          <img :src="`http://ddragon.leagueoflegends.com/cdn/12.10.1/img/spell/${champion.spells[0].image.full}`" alt="">
                        </span>
                      </span>
                      <span class="option-line"></span>
                      <span class="option-bullet-container">
                        <span class="bullet"></span>
                      </span>
                    </button>
                    <button @click='updateSpellInfos' data-spell-type="W" :data-spell-name="champion.spells[1].name" :data-spell-desc="champion.spells[1].description" class="option">
                      <span class="option-icon">
                        <span class="option-icon-content">
                          <img :src="`http://ddragon.leagueoflegends.com/cdn/12.10.1/img/spell/${champion.spells[1].image.full}`" alt="">
                        </span>
                      </span>
                      <span class="option-line"></span>
                      <span class="option-bullet-container">
                        <span class="bullet"></span>
                      </span>
                    </button>
                    <button @click='updateSpellInfos' data-spell-type="E" :data-spell-name="champion.spells[2].name" :data-spell-desc="champion.spells[2].description" class="option">
                      <span class="option-icon">
                        <span class="option-icon-content">
                          <img :src="`http://ddragon.leagueoflegends.com/cdn/12.10.1/img/spell/${champion.spells[2].image.full}`" alt="">
                        </span>
                      </span>
                      <span class="option-line"></span>
                      <span class="option-bullet-container">
                        <span class="bullet"></span>
                      </span>
                    </button>
                    <button @click='updateSpellInfos' data-spell-type="R" :data-spell-name="champion.spells[3].name" :data-spell-desc="champion.spells[3].description" class="option">
                      <span class="option-icon">
                        <span class="option-icon-content">
                          <img :src="`http://ddragon.leagueoflegends.com/cdn/12.10.1/img/spell/${champion.spells[3].image.full}`" alt="">
                        </span>
                      </span>
                      <span class="option-line"></span>
                      <span class="option-bullet-container">
                        <span class="bullet"></span>
                      </span>
                    </button>
                    <div class="baseline">
                    </div>
                    <div class="ability-info">
                      <ol class="ability-info-list">
                        <li class="ability-info-item">
                          <h6 class="ability-info-item-type"></h6>
                          <h5 class="ability-info-item-name"></h5>
                          <p class="ability-info-item-desc"></p>
                        </li>
                      </ol>
                    </div>
                    <div class="ability-info">
                      <ol class="ability-info-list">
                        <li v-show='showPassive' class="ability-info-item">
                          <h6 class="ability-info-item-type">Passiva</h6>
                          <h5 class="ability-info-item-name">{{ champion.passive.name }}</h5>
                          <p class="ability-info-item-desc" v-html="champion.passive.description">{{ champion.passive.description }}</p>
                        </li>
                      </ol>
                    </div>
                  </div>
                  <div class="side-fill">
                    <div class="baseline-right"></div>
                  </div>
                </div>
              </div>
            </div>
            <div class="preview-wrapper">
              <div class="wrap-preview-wrapper">
                <div class="preview-wrapper-inner"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="background-icon">
        <svg class="svg-bg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
          <path d="M67.84 56.35v5.5c8.62-8.62 14.37 0 14.37 0C112.14 40.78 90.35 2 90.35 2s-.72 17.24-15.08 27.77v16.52c-.24 4.79-3.84 7.9-7.43 10.06M17.79 62.09s4.07-6.46 10.78-2.63L20.91 48.2l6.7-16c-17.24-10.54-18-29.93-18-29.93S-12.14 41 17.79 62.09M26.89 83.89l5.51-18.68-.24-.48L19.23 77.9A17.78 17.78 0 017.5 83.17H3l-1 2.39 12 11.5zM92.27 83.89a16.24 16.24 0 01-11.74-5.27L68.8 66.88l3.83 17.72L85.8 98l12-11.49-1-2.4zM55.87 42.7c0 .24-.24.48-.24.71h.72c5.75.48 7.66 2.64 9.1 7.67a9.35 9.35 0 002.39-1.92c1-1 1.68-1.67 1.68-2.63V28.09a2 2 0 00-1.68-1.92l-31.37-5.74H36a2.39 2.39 0 00-2.39 2.39v6.71l24.9 3.35z"></path>
          <path d="M60.18 54c-1.2-5.27-1.44-4.55-5.75-4.79L40.78 48v-3.87h5.51A4.09 4.09 0 0050.36 41l1-3.35L32.4 35l-5 12.22 11.74 17-5.54 18.47L49.88 98l16.53-15.07s-6.23-28.5-6.23-29M49.88 2.23l-4.79 10.29 4.79 3.83 4.79-3.83zM62.1 9.41l1.43 6h6l2.87-11zM30.25 15.4h6l.24-.72 1.2-5.27-10.3-5z"></path>
        </svg>
      </div>
    </section>
  </div>
</template>

<script>
import JQuery from 'jquery'
window.$ = JQuery

export default {
    async asyncData({ params, $axios }) {
        const json = await $axios.$get(
            `https://ddragon.leagueoflegends.com/cdn/12.9.1/data/it_IT/champion/${params.id}.json`
            )
        const champion = json.data[params.id]
        return { champion }
    },
    
  data () {
    return {
      showPassive: true,
    }
  },
  methods: {
    updateSpellInfos(event) {
      window.$('.ability-info-item-type').empty().append(event.currentTarget.getAttribute('data-spell-type'))
      window.$('.ability-info-item-name').empty().append(event.currentTarget.getAttribute('data-spell-name'))
      window.$('.ability-info-item-desc').empty().append(event.currentTarget.getAttribute('data-spell-desc'))
      window.$(event.currentTarget).addClass('is-active')
      window.$('.option').not(event.currentTarget).removeClass('is-active')
    }
  }
}
</script>

<style lang="scss" scoped>
.general {
  outline: none;
}
.wrapper {
  position: relative;
  min-height: 75vh;
  padding: 0px 0px 75px;
  background: #0a0a0c;
  @media (max-width: 599px) {
    padding-bottom: 1.25rem;
  }
}
.background-asset{
  position: relative;
  left: 0px;
  top: 0px;
  width: 100%;
  height: 80vh;
  max-height: 800px;
  overflow: hidden;
} 
.background-img {
  position: relative;
  left: -5%;
  top: -5%;
  width: 110%;
  height: 110%;
  &::after {
    content: "";
    position: absolute;
    left: 0px;
    bottom: -10%;
    width: 100%;
    height: 50%;
    background: linear-gradient(transparent, rgb(10, 10, 12) 70%);
    @media (max-width: 599px) {
      height: 80%;
      background: linear-gradient(transparent, rgb(10, 10, 12) 70%);
    }
  }
}
img {
  border-style: none;
}
.divider {
  display: block;
  margin: 0 auto;
  max-width: 100%;
}
.blurimg {
  object-fit: cover;
  object-position: center 20%;
  display: block;
  width: 100%;
  height: 100%;
  filter: blur(8px);
  animation: 3000ms cubic-bezier(0.215, 0.61, 0.355, 1) 500ms 1 normal;
  @media (max-width: 599px) {
    filter: blur(8px);
  }
}
.clearimg {
  object-position: center 20%;
  position: absolute;
  left: 50%;
  top: 50%;
  margin-top: 5%;
  transform: translate(-50%, -50%);
  animation: 2000ms cubic-bezier(0.215, 0.61, 0.355, 1) 700ms 1 normal;
  @media (max-width:500px) {
    width: 88%;
    top: 17.5%;
  }
}
.intro-wrapper {
  position: absolute;
  top: 31%;
  display: flex;
  width: 100%;
  height: 100%;
}
.right-content {
  flex: 1 1 100%;
  min-width: 0px;
  &::after {
    display: block;
    content: "";
    width: 60px;
    flex: 0 0 auto;
  }
}
.left-title {
  position: relative;
  width: 60px;
  flex: 0 0 auto;
  @media (max-width: 599px) {
    display: none;
  }
}
.left-text-container {
  z-index: 10;
  position: relative;
  display: inline-block;
  margin-left: 50%;
  transform: translateX(-50%);
}
.left-text {
  text-transform: uppercase;
  padding-top: 100%;
  transform: rotate(-90deg) translate(-100%, -50%);
  transform-origin: left top;
  white-space: nowrap;
  color: rgb(255, 255, 255);
  font-size: 0.625rem;
  letter-spacing: 0.25em;
  font-weight: bold;
  &::after {
    content: "";
    display: inline-block;
    vertical-align: middle;
    width: 1.4em;
    height: 1px;
    margin-left: 0.5em;
    background-color: currentcolor;
  }
}
.dock {
  position: relative;
  margin: -5.625rem 3.75rem 0px;
  @media (max-width: 599px) {
    margin: -28.7rem 0px 0px;
  }
}
.name-container {
  position: relative;
  top: -5rem;
  margin-bottom: -5rem;
}
.name-wrapper {
  position: relative;
  z-index: 1;
  text-align: center;
  color: rgb(255, 255, 255);
}
.heading {
  margin: 0px;
  font-weight: normal;
  font-size: 2em;
  @media (max-width: 599px) {
    top: -2.6875rem;
    margin-bottom: -2.6875rem;
  }
}
.intro {
  text-transform: uppercase;
  text-align: center;
  font-style: italic;
  line-height: 1.1;
  display: block;
  font-size: 1.5rem;
  font-weight: 600;
  letter-spacing: 0.1em;
  @media (max-width: 599px) {
    font-size: 1rem;
  }
}
.reveal-wrapper {
  display: inline-block;
}
.intro-name {
  text-transform: uppercase;
  font-size: calc(43.27px + 2.12vw);
  font-style: italic;
  line-height: 1.1;
  display: block;
  font-family: BeaufortforLOL-Bold, sans-serif;
  font-weight: 800;
  letter-spacing: 0.03em;
  @media (max-width: 599px) {
    font-size: calc(22.24px + 4.3vw);
  }
}
.champ-name {
  display: block;
  padding: 0px 15px 10px;
  margin-bottom: -10px;
}
.info-wrapper {
  position: relative;
  display: flex;
  border: 1px solid rgba(208, 168, 92, 0.3);
  border-top: none;
  @media (max-width: 1023px) {
    flex-wrap: wrap;
  }
}
.specs {
  box-sizing: border-box;
  width: 50%;
  padding: 3.75rem;
  @media (max-width: 599px) {
    padding: 1.25rem 0.625rem;
    width: 100%;
  }
}
.specs-list {
  list-style: none;
  padding: 0px;
  margin: 0px;
  display: flex;
  justify-content: space-around;
  width: 100%;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  padding-inline-start: 40px;
}
.specs-item {
  display: block;
  text-align: center;
  color: rgb(208, 168, 92);
  font-size: 0.625rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}
.specs-item-icon {
  display: block;
  width: 50px;
  height: 50px;
  position: relative;
  margin: 0px auto;
}
.specs-icon {
  overflow: hidden;
  display: inline-block;
  vertical-align: middle;
  width: 36px;
  height: 36px;
  padding: 7px;
  fill: rgb(208, 168, 92);
}
.specs-item-type {
  display: block;
  width: 100%;
  margin-top: 0.9375rem;
  color: rgb(255, 255, 255);
}
.specs-item-value {
  display: block;
  width: 100%;
  margin-top: 0.125rem;
  color: rgb(208, 168, 92);
  font-weight: normal;
}
.info-divider {
  width: 1px;
  margin: 2.5rem 0px;
  background: rgba(208, 168, 92, 0.3);
  transform-origin: center top;
  @media (max-width: 599px) {
    width: calc(100% - 6.25rem);
  }
  @media (max-width: 1023px) {
    height: 1px;
    margin: 0px auto;
  }
}
.desc {
  box-sizing: border-box;
  display: flex;
  -webkit-box-align: center;
  align-items: center;
  width: 50%;
  padding: 3.75rem;
  @media (max-width: 599px) {
    padding: 1.25rem 1.25rem 2.5rem;
    font-size: 10px;
    letter-spacing: 0.04em;
    width: 100%;
  }
}
.p-desc {
  line-height: 1.28571;
  max-width: 100%;
  margin-top: 0px;
  margin-bottom: 0px;
  color: rgb(255, 255, 255);
  font-size: 0.875rem;
  letter-spacing: 0.08em;
  display: block;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
}
.section-inner {
  box-sizing: border-box;
  max-width: 1335px;
  padding: 0px 3.75rem;
  margin: 0px auto;
  @media (max-width: 1200px) {
    padding: 0px 0.625rem;
  }
}
.champions-button-container {
  position: absolute;
  top: 40px;
  right: 30px;
  font-family: BeaufortforLOL-Bold, sans-serif;
  font-weight: 700;
  font-size: 11px;
  background-color: rgba(10,10,12,.6);
  letter-spacing: .3em;
  line-height: 1.1;
  text-align: left;
  text-transform: uppercase;
  border: 1px solid #c4b998;
  box-shadow: 0 0 16px 14px rgb(0 0 0 / 20%);
  &:hover {
    border: 1px solid #937341;
    transition-timing-function: ease, step-start, ease;
    transform: scale(1.05);
  }
  @media (max-width: 599px) {
    width: 36px;
    height: 36px;
    top: 26px;
    right: 20px;
  }
}
.champions-button-link {
  cursor: pointer;
  color: #c4b998;
  position: relative;
  display: block;
  height: 100%;
  padding: 10px 20px;
  text-decoration: none;
  @media (max-width: 599px) {
    padding: 0px;
  }
}
.champions-button-text {
  vertical-align: middle;
  padding-right: 10px;
  @media (max-width: 599px) {
    line-height: 1.1;
    font-size: 0px;
    color: transparent;
  }
}
.champions-button-icon {
  fill: #c4b998;
  height: 14px;
  width: 14px;
  vertical-align: middle;
  overflow: hidden;
  @media (max-width: 599px) {
    position: absolute;
    width: 18px;
    height: 18px;
    right: 9px;
    top: 9px;
  }
}
.scroll-indicator {
  position: absolute;
  bottom: 0px;
  left: 50%;
  transform: translate(-50%, 0px);
  stroke: rgba(208, 168, 92, 0.3);
  width: 17;
  height: 58;
  fill: none;
  overflow: hidden;
  @media (max-width: 1023px) {
    display: none;
  }
}
.abilities {
  position: relative;
  padding: 75px 0px 15rem;
  display: block;
  @media (max-width: 1023px) {
    padding: 0px 0px 3.75rem;
    height: 600px;
  }
}
.mobile-title {
display: none;
width: 100%;
margin: -1px 0px 0px;
color: rgb(255, 255, 255);
letter-spacing: 0.05em;
font-family: "BeaufortforLOL-Bold", sans-serif;
font-weight: 800;
text-align: center;
font-size: 1.875rem;
font-style: italic;
text-transform: uppercase;
margin-block-start: 0.83em;
margin-block-end: 0.83em;
margin-inline-start: 0px;
margin-inline-end: 0px;
  @media (max-width: 1023px) {
    display: block;
  }
}
.abilities-wrapper {
  display: flex;
  width: 100%;
  height: 100%;
}
.abilities-content {
  flex: 1 1 100%;
  min-width: 0px;
  &::after {
    display: block;
    content: "";
    width: 60px;
    flex: 0 0 auto;
  }
}
.abilities-inner {
  position: relative;
  z-index: 1;
  box-sizing: border-box;
  display: flex;
  max-width: 2040px;
  padding: 0px 60px 0px 0px;
  @media (max-width: 1023px) {
    flex-flow: column-reverse wrap;
    padding: 0px 20px;
  }
}
.selector-wrapper {
  flex: 2 1 120%;
  padding-top: 5.625rem;
  @media (max-width: 599px) {
    padding: 20px 0px;
  }
  @media (max-width: 1023px) {
    flex: 1 1 auto;
    box-sizing: border-box;
    width: 100%;
  }
}
.wrapwrapper {
  width: 100%;
}
.wrapper-inner {
  position: relative;
  width: 100%;
  display: flex;
  @media (max-width: 599px) {
    width: calc(100% + 4px);
    margin: 0px -2px;
  }
  @media (max-width: 1023px) {
    padding-bottom: 250px;
    width: calc(100% + 10px);
    margin: 0px -5px;
    overflow: visible;
  }
}
.side-fill {
  flex: 1 1 auto;
  position: relative;
}
.baseline-left {
  left: auto;
  right: 0px;
  width: 200%;
  min-width: 120px;
  position: absolute;
  bottom: 16.5px;
  height: 1px;
  background-color: rgba(208, 168, 92, 0.3);
  @media (max-width: 1023px) {
    display: none;
  }
  @media (max-width: 599px) {
    bottom: 40.5px;
  }
}
.option-list {
  position: relative;
  display: inline-flex;
  @media (max-width: 1023px) {
    width: 100%;
    display: flex;
    -webkit-box-pack: justify;
    justify-content: space-between;
    padding: 30px 0px;
  }
}
.abilities-title {
  position: absolute;
  left: 15px;
  bottom: calc(100%);
  margin-top: 0px;
  margin-bottom: 40px;
  color: rgb(255, 255, 255);
  letter-spacing: 0.05em;
  font-family: "Beaufort for LOL", serif;
  font-weight: 800;
  font-size: 3.75rem;
  display: block;
  font-style: italic;
  text-transform: uppercase;
  margin-block-start: 0.83em;
  margin-block-end: 0.83em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  @media (max-width: 1023px) {
    font-size: calc(22.24px + 4.3vw);
    margin-left: -12px;
  }
}
.option {
  cursor: pointer;
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  -webkit-box-align: stretch;
  align-items: stretch;
  padding: 12px;
  border: 0px;
  background-color: transparent;
  color: #463A24;
  overflow: visible;
  &:hover .bullet {
    transition: color 600ms ease 0s;
    color: rgb(208, 168, 92);
  }
  @media (max-width: 1023px) {
    margin-left: 0px;
    flex: 0 0 auto;
    min-width: auto;
    min-height: auto;
    padding: 0px;
    white-space: nowrap;
  }
}
.is-active .option-icon-content {
  transform: translateY(0px) scale(1, 1);
  transition: transform 0.4s cubic-bezier(0.215, 0.61, 0.355, 1) 0s;
  border: 2px solid #d0a85c;
  &:hover {
    transform: none;
  }
}
.is-active .option-line {
  opacity: 1;
  transform: scaleY(1);
  transition-duration: 400ms;
  transition-delay: 400ms;
}
.is-active .bullet {
  color: rgb(208, 168, 92);
  transform: scale(1.5);
  transform-origin: center;
  transition-duration: 2s;
  transition-timing-function: ease-in-out;
}
.option-icon {
  position: relative;
  display: block;
  width: 70px;
  height: 70px;
  margin: 0px auto 10px;
  @media (max-width: 599px) {
    width: 55px;
    height: 55px;
  }
  @media (max-width: 1023px) {
    margin: 0px;
  }
}
.option-icon-content {
  position: absolute;
  top: 5px;
  left: 5px;
  width: 60px;
  height: 60px;
  transform: translateY(20px) scale(1, 1);
  will-change: transform;
  transform-origin: center bottom;
  transition: transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1) 0s, fill 0.2s ease-in-out 0s;
  &:hover {
    transform: translateY(15px) scale(1, 1);
    transition: transform 0.2s cubic-bezier(0.215, 0.61, 0.355, 1) 0s;
  }
  @media (max-width: 599px) {
    width: calc(100% - 4px);
    top: 2px;
    left: 2px;
    transform: none;
  }
  @media (max-width: 1023px) {
    height: auto;
  }
}
.option-icon-content img {
  width: 100%;
  height: 100%;
}
.option-line {
  opacity: 1;
  transform: scaleY(1);
  display: block;
  width: 1px;
  height: 20px;
  margin: 0px auto;
  background-color: rgb(208, 168, 92);
  opacity: 0;
  transform: scaleY(0);
  will-change: transform;
  transform-origin: center bottom;
  transition-timing-function: cubic-bezier(0.165, 0.84, 0.44, 1);
  @media (max-width: 1023px) {
    display: none;
  }
}
.option-bullet-container {
  display: block;
  position: relative;
  width: calc(100% + 24px);
  margin-top: 5.5px;
  margin-left: -12px;
  z-index: 1;
  &::before {
    left: 0px;
  }
  &::before, &::after {
    content: "";
    position: absolute;
    bottom: 4.5px;
    width: 50%;
    height: 1px;
    background-color: currentcolor;
    z-index: -1;
    transition: width 0ms ease 0ms;
  }
  @media (max-width: 1023px) {
    display: none;
  }
}
.bullet {
  opacity: 1;
  margin: 0px auto;
  display: block;
  width: 9px;
  height: 9px;
  background-color: currentcolor;
  border-radius: 50%;
  }
.baseline {
  position: absolute;
  bottom: 16.5px;
  left: 0px;
  width: 100%;
  height: 1px;
  background-color: transparent;
  @media (max-width: 1023px) {
    display: none;
  }
  @media (max-width: 599px) {
    bottom: 40.5px;
  }
}
.ability-info {
  position: absolute;
  top: 100%;
  left: 2.8125rem;
  right: 0px;
  color: rgb(255, 255, 255);
  @media (max-width: 1023px) {
    left: 4px;
    right: 4px;
  }
}
.ability-info-list {
  list-style: none;
  padding: 0px;
  position: relative;
  margin: 1.875rem 0px 0px;
  display: block;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  padding-inline-start: 40px;
  @media (max-width: 599px) {
    margin: 0px;
  }
}
.ability-info-item {
  position: absolute;
  left: 0px;
  top: 0px;
  width: 100%;
  pointer-events: none;
  opacity: 1;
  transition: opacity 0.4s cubic-bezier(0.645, 0.045, 0.355, 1) 0s;
}
.ability-info-item-type {
  margin-top: 0px;
  font-size: 0.625rem;
  text-transform: uppercase;
  line-height: 1.1;
  font-weight: normal;
  letter-spacing: 0.15em;
  color: #c4b998;
}
.ability-info-item-type h6 {
  display: block;
  margin-bottom: 0px;
  margin-block-start: 2.33em;
  margin-block-end: 2.33em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
}

.ability-info-item-name {
  margin-top: 0px;
  margin-bottom: 0.5rem;
  font-size: 1.125rem;
  line-height: 1.11111;
  font-weight: 700;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  @media (max-width: 599px) {
    margin-top: 1rem;
  }
}
.ability-info-item-name h5 {
  display: block;
  margin-block-start: 1.67em;
  margin-block-end: 1.67em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
}
.ability-info-item-desc {
  margin-top: 6px;
  font-size: 0.875rem;
  line-height: 1.4;
  letter-spacing: 0.05em;
}
.ability-info-item-desc p {
  display: block;
  margin-bottom: 0px;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
}
.baseline-right {
  position: absolute;
  bottom: 16.5px;
  left: 0px;
  width: 570%;
  height: 1px;
  object-fit: fill;
  background-color: #463A24;
  @media (max-width: 1023px) {
    display: none;
  }
@media (max-width: 599px) {
    bottom: 40.5px;
  }
}
.preview-wrapper {
  box-sizing: border-box;
  width: 100%;
  flex: 1 1 100%;
  padding-top: 3.75rem;
  @media (max-width: 599px) {
    display: none;    
  }
}
.wrap-preview-wrapper {
  width: 100%;
}
.preview-wrapper-inner {
  position: relative;
  width: 100%;
  padding-top: 56.25%;
}
.background-icon {
  position: absolute;
  inset: -1px 0px 0px;
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  align-items: center;
  background-color: #0a0a0c;
}
.svg-bg {
  height: calc(100% - 30px);
  fill: rgba(208, 168, 92, 0.04);
  overflow: hidden;
}
</style>