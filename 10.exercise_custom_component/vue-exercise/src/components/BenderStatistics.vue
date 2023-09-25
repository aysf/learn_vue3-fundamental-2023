<script>
export default{
    props: ["charactersParam"],
    computed: {
    earthBenderList() {
      return this.characters.filter((char) => char.element.indexOf('Earth') > -1)
    },
    benderStatistics() {
      const elements = ['Air', 'Earth', 'Fire', 'Water']
      const statistics = {
        Air: 0,
        Earth: 0,
        Fire: 0,
        Water: 0
      }

      this.charactersParam.forEach((char) => {
        elements.forEach((element) => {
          if (char.element.indexOf(element) > -1) {
            statistics[element] += 1
          }
        })
      })

      return statistics
    }
  }
}
</script>

<template>
<h2>Statistics</h2>
  <ul></ul>
  {{ benderStatistics }}

  <h2>show characters in the list</h2>
  <ul>
    <li v-for="char in charactersParam">
      <p>{{ char.name }}</p>
      <button @click="favoriteCharacters(char)">⭐ Favorite</button>
    </li>
  </ul>
</template>