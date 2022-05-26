<template>
  <div>
    <p v-if="$fetchState.pending">Fetching champions...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div v-else>
      <h1>Test</h1>
      <ul>
        <li v-for="champion of champions">{{ champion.id }}</li>
      </ul>
      <button @click="$fetch">Refresh</button>
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
</script>