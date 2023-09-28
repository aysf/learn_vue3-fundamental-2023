<script>
export default {
  beforeCreate() {
    console.log('beforeCreate')
    console.log(this.pokedex)
  },
  data: () => ({
    pokedex: [1, 2, 3]
  }),
  methods: {
    async fetchPokemon() {
      this.pokedex = await fetch('https://pokeapi.co/api/v2/pokemon?limit=155').then((response) =>
        response.json()
      )
    }
  },

  created() {
    console.log('created')
    console.log(this.pokedex)
    this.fetchPokemon()
  }
}
</script>

<template>
  <h1>Pokemon</h1>

  <pre>{{ pokedex }}</pre>
  <!-- <button @click="fetchPokemon">fetch</button> -->
</template>

<style></style>
