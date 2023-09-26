<script>
export default {
  props: {
    charactersProps: {
      type: Array,
      required: true
    }
  },
  computed: {
    earthBenderList() {
      return this.charactersProps.filter((char) => char.element.indexOf('Earth') > -1)
    },
    benderStatistics() {
      const elements = ['Air', 'Earth', 'Fire', 'Water']
      const statistics = {
        Air: 0,
        Earth: 0,
        Fire: 0,
        Water: 0
      }

      this.charactersProps.forEach((char) => {
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
</template>
