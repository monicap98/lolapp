<template>
  <div class="home">
    <!-- Hero -->
    <Hero />

    <!-- Champions -->
    <div class="container champions">
      <div id="champion-grid" class="champions-grid">
        <div class="champion" v-for="champion in champions" :key="champion.id">
        <div class="champion-img">
          <img
            :src="'http://ddragon.leagueoflegends.com/cdn/img/champion/loading/Warwick_0'"
            alt=""
          />
          <p class="difficulty">{{champion.difficulty}}</p>
          <p class="blurb">{{champion.blurb}}</p>
        </div>
          <div class="info">
            <p class="title">{{champion.name}}</p>
            <p class="subtitle">{{champion.title}}</p>
            <NuxtLink
              class="button button-light"
              :to="{name: 'champions_championid', params: {id : champion.id}}">
              Scopri di più
            </NuxtLink>
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
        champions: []
      }
    },
    async fetch() {
      this.champions = await fetch(
        'https://ddragon.leagueoflegends.com/cdn/12.9.1/data/it_IT/champion'
      ).then(res => res.json())
    }
  }
/*  
import axios from 'axios'
export default {
  data() {
    return {
      champions: [],
    }
  },
  async fetch() {
    await this.getChampions()
  },
  methods: {
    async getChampions() {
      const data = axios.get('https://ddragon.leagueoflegends.com/cdn/12.9.1/data/it_IT/champion.json')
      const result = await data
      result.data.results.forEach(champion => {
        this.champions.push(champion)        
      });
    },
  },
}*/
</script>

<style lang="scss" scoped>
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
          .overview {
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
</style>