<script>
export default {
  data: () => ({
    pokedex: [1,2,3]
  }),
  methods: {
    async fetchPokemon() {
      this.pokedex = await fetch("https://pokeapi.co/api/v2/pokemon?limit=155").then(response => response.json())
    },
  }
}
</script>

<template>
 <h1>Pokemon</h1>

<pre>{{pokedex}}</pre>
<button @click="fetchPokemon">fetch</button>

</template>

<style>

</style>
