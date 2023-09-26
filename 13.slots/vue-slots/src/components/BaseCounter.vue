<script>
export default {
  data: () => {
    return {
      countTitle: 'Count Standard',
      count: 0,
      incrementAmount: 3
    }
  },
  methods: {
    incrementCount() {
      this.count += this.incrementAmount
    },
    decrementCount() {
      this.count--
    }
  },
  computed: {
    displayTitle() {
      if (this.count > 20) {
        return 'Count Standard Very Long'
      } else {
        return 'Count Standard'
      }
    }
  }
}
</script>

<template>
  <h1>Handling event</h1>
  <h1>{{ displayTitle }}</h1>
  <h2>count: {{ count }}</h2>
  <label for="incrementAmount">Increment/decrement by</label><br />
  <input type="number" v-model="incrementAmount" />
  <br /><br />
  <button v-on:click="incrementCount">+</button>
  <button v-on:click="decrementCount">-</button>
</template>
