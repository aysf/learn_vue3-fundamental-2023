<script>
export default {
  props: {
    characterProps: {
      type: Array,
      required: true
    }
  },
  computed: {
    earthBenderList() {
      return this.characterProps.filter((char) => char.element.indexOf('Earth') > -1)
    },
    benderStatistics() {
      const elements = ['Air', 'Earth', 'Fire', 'Water']
      const statistics = {
        Air: 0,
        Earth: 0,
        Fire: 0,
        Water: 0
      }

      this.characterProps.forEach((char) => {
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

  {{ benderStatistics }}

  <h2>show characters in the list</h2>
  <ul>
    <li v-for="char in characterProps">
      <p>{{ char.name }}</p>
      <button @click="favoriteCharacters(char)">⭐ Favorite</button>
    </li>
  </ul>
</template>
