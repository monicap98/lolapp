<template>
  <div class="general">  
    <div class="wrapper">   
      <div class="image-container">
        <div class="blurbg"><img :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/splash/${champion.id}_0.jpg`" alt=""></div>
        <div class="clearbg"><img :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/splash/${champion.id}_0.jpg`" alt=""></div>
      </div>
      <div class="title-container">
        <div class="champion-name">{{ champion.name }}</div>
        <div class="champion-title">{{ champion.title }}</div>
      </div>
      <div class="text-container">
        <div class="attribute"><p>{{ champion.tags }}</p></div>
        <div class="divide-line"></div>
        <div class="story"><p>{{ champion.lore }}</p></div>
      </div>
    </div>

    <div class="ability-wrapper">
      <div class="left">
        <div class="title">Abilità</div>
        <div class="brand">Abilità</div>
        <div class="ability-select"></div>
        <div class="ability-info">
          <div class="item">
            <div class="type">{{ champion.spells.id }}</div>
            <div class="name">{{ champion.spells.name }}</div>
            <div class="description">{{ champion.spells.description }}</div>
          </div>
        </div>
      </div>
      <div class="right">
        <div class="ability-show"></div>
      </div>
      <div class="background">
        <svg viewBox="0 0 100 100">
          <path d="M28.69 27.25h6.94l1.92-6.94-13.41-7.91zM71.31 27.25l4.55-14.85-13.41 7.91 1.92 6.94zM71.31 35.39c-1.43 0-12.21-3.83-12.21-3.83L50 42.34l-9.1-10.78s-10.54 3.83-12.21 3.83c-7.67 0-4.79-7.18-4.79-7.18S4.26 48.32 2.11 64.13c0 0 5.74-8.86 24.42-13.17a26.22 26.22 0 0013.89 12.93c-.72-3.11-1.44-6.71-2.15-10.06a22.36 22.36 0 01-3.84-4.31c.72 0 7.19-.72 8.15-.72.71 2.64 4.55 28.74 4.55 28.74l-7 10.3v10L50 93.82l9.82 4.07V87.6l-7-10.3s3.84-26.1 4.55-28.74c.72 0 7.19.72 8.15.72a16.52 16.52 0 01-3.84 4.31 98.08 98.08 0 00-2.15 10.06 25.33 25.33 0 0013.94-12.93c18.68 4.55 24.42 13.17 24.42 13.17C95.74 48.32 76.1 28 76.1 28s2.88 7.42-4.79 7.42"></path>
          <path d="M50 2.11l-7.66 21.31h.24L50 33.24l7.42-9.82h.24z"></path>
        </svg>
      </div>
    </div>

    <div class="skin-wrapper">
      <div class="skin-title">Aspetti disponibili</div>
      <div class="skin-brand">Aspetti disponibili</div>
      <div class="skin-container">
        <div class="skin-detail">
          <div class="skin-item">
            <div class="skin-image">
              <img :src="`http://ddragon.leagueoflegends.com/cdn/img/champion/splash/${champion.id}_0.jpg`" alt="">
            </div>
          </div>
        </div>
        <div class="skin-select"></div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
    async asyncData({ params, $axios }) {
        const json = await $axios.$get(
            `https://ddragon.leagueoflegends.com/cdn/12.9.1/data/it_IT/champion/${params.id}.json`
            )
        const champion = json.data[params.id]
        return { champion }
    },
}
</script>

<style lang="scss" scoped>

.wrapper {
  position: relative;
  background-color: rgb(0, 9, 19)  
}
.image-container {
    position: relative;
    left: 0;
    top: 0;
    width: 100%;
    height: 80vh;
    max-height: 800px;
    overflow: hidden;
    .blurbg {
      position: absolute;
      display: block;
      left: -5%;
      top: -5%;
      width: 110%;
      height: 110%;

      filter: blur(8px);
      mask-image: linear-gradient(rgb(0, 0, 0) 0%, rgba(0, 0, 0, 0) 98%);
    }
    .clearbg {
      position: absolute;
      display: block;
      width: 100%;
      height: 100%;
      padding: 0px 3.75rem;

      mask-image: linear-gradient(rgb(0, 0, 0) 65%, rgba(0, 0, 0, 0) 98%);
      object-fit: cover;
    }
}
.title-container {
  position: relative;
  display: block;
  padding: 0px 100px;
  margin-top: -5rem;
  text-transform: uppercase;

  &::before {
    content: '';
    position: relative;
    display: inline-block;
    top: 50%;
    width: 25%;
    height: 1px;

    background-color: rgba(255, 255, 255, 0.2);
  }
  .champion-name {
    margin: 0 auto;
    text-align: center;
    font-style: italic;
    font-family: 'Beaufort for LOL', serif;
    font-size: 3rem;
    font-weight: 800;
    letter-spacing: 0.03em;
    color: #fff;
  }
  .champion-title {
    margin: 0 auto;
    text-align: center;
    font-style: italic;
    font-size: 1.5rem;
    font-weight: 600;
    letter-spacing: 0.1em;
    color: #fff;
  }
}
.text-container {
  display: flex;
  position: relative;
  padding: 70px;
  margin: 0 100px 0 100px;

  border: 1px solid rgba(255, 255, 255, 0.2);
  border-top: none;
  .attribute {
    flex: 1;
    padding: 3.75rem;
  }
  .divide-line {
    width: 1px;

    background-color: rgba(255, 255, 255, 0.2);
  }
  .story {
    flex: 1;
    padding: 3.75rem;
  }
}
.ability-wrapper {
  position: relative;
  display: flex;
  justify-content: space-around;
  align-items: stretch;
  padding: 60px 100px 200px 0px;

  background-color: rgb(0, 9, 19);

  @media screen and (max-width: 1000px) {
    flex-direction: column-reverse;
    padding: 60px 0px;
  }
  .left {
    flex: 2 1 120%;
    position: relative;
    z-index: 2;
  }
  .title {
    padding: 0px 0px 40px 6vw;
    font-family: 'Beaufort for LOL';
    font-weight: bold;
    font-size: 3.75rem;
    font-style: italic;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    
    color: #fff;
    
    @media screen and (max-width: 1000px) {
    display: none;
    }
  }
  .brand {
    position: absolute;
    top: 50%;
    left: 0;
    width: fit-content;
    padding: 20px 0px 0px 100px;

    font-size: 0.625rem;
    letter-spacing: 0.25em;
    font-family: 'Spiegel';
    text-transform: uppercase;
    color: #fff;

    transform: rotate(-90deg);
    transform-origin: left top;

    @media screen and (max-width: 600px) {
      display: none;
    }
  }
  .ability-info {
    padding: 30px 30px 0px 7vw;

    &::after {
      content: '';
      display: block;
      clear: left;
    }

    @media screen and (max-width: 1000px) {
      padding: 0px 15%;
    }

    @media screen and (max-width: 600px) {
      padding: 0px 30px;
    }
    .item {
      display: block;
      width: 100%;
      float: left;

      list-style: none;

      transition: opacity 1s;
    }
    .type {
      font-size: 0.625rem;
      color: rgb(126, 126, 126);
    }
    .name {
      margin-top: 0.375rem;

      font-size: 1.125rem;
      color: #fff;
    }
    .description {
      margin-top: 0.375rem;

      font-size: 0.875rem;
      color: #fff;
      line-height: 1.4;
      letter-spacing: 0.05em;
    }
  }
  .right {
    flex: 1 1 100%;
    z-index: 2;
  }
  .background {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;

    text-align: center;

    & > svg {
      position: relative;
      display: inline-block;
      height: 80%;
      top: 10%;
      fill: rgb(7, 18, 26);
    }

    @media screen and (max-width: 600px) {
      & > svg {
        top: 50%;
        height: 50%;
      }
    }
  }
}
.skin-wrapper {
  position: relative;
  padding: 60px;

  @media screen and (max-width: 1000px) {
    background-color: rgb(0, 9, 19);
  }

  @media screen and (max-width: 600px) {
    padding: 60px 0px;
  }
  .skin-title {
    display: none;
    padding-bottom: 20px;

    font-size: 20px;
    font-style: italic;
    font-family: 'Beaufort for LOL', 'Arial Narrow', Arial, sans-serif;
    font-weight: bold;
    letter-spacing: 0.05em;
    text-align: center;
    color: #fff;

    @media screen and (max-width: 600px) {
      display: block;
    }
  }
  .skin-brand {
    position: absolute;
    left: 0;
    top: calc(50% + 100px);
    width: 200px;
    height: 60px;
    line-height: 60px;

    font-size: 0.625rem;
    font-family: 'Spiegel', 'Arial Narrow', Arial, sans-serif;
    font-weight: bold;
    letter-spacing: 0.25em;
    text-align: center;

    transform: rotate(-90deg);
    transform-origin: left top;

    @media screen and (max-width: 1000px) {
      color: rgba(255, 255, 255, 0.6);
    }

    @media screen and (max-width: 600px) {
      display: none;
    }
  }
  .skin-container {
    position: relative;
    width: 100%;
    max-width: 97.5rem;
    margin: 0 auto;
    overflow: hidden;
  }
  .skin-detail {
    position: relative;
    padding: 0;

    background-color: #000;

    &::after {
      content: '';
      display: block;
      clear: both;
    }
    .skin-item {
      position: relative;
      display: block;
      width: 100%;
      float: left;

      list-style: none;
    }
    .skin-image {
      display: block;
      width: 100%;
    }
  } 
}
</style>