<script>
export default {
  data() {
        return {
                  message: 'Hello from vue!!',
                  listOfNumber: [1,2,3,4],
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
            watch: {
                count(newValue) {
                    if (newValue > 20) {
                        this.countTitle += ' very big'
                    }
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
  <div id="app">
    <h1>if/else directive</h1>
        <p v-if="message.length % 2 === 0">Even: {{ message.toUpperCase() }}</p>
        <p v-else>Odd: {{ message }}</p>

        <h1>list directive</h1>
        <ul><li v-for="num in listOfNumber">{{ num * Math.random() }}</li></ul>

        <h1>Handling event</h1>
        <h1> {{ displayTitle }} </h1>
        <h2>count: {{ count }}</h2>
        <label for="incrementAmount">Increment/decrement by</label><br>
        <input type="number" 
            v-model="incrementAmount">
        <br><br>
        <button v-on:click="incrementCount">+</button> 
        <button v-on:click="decrementCount">-</button>
  </div>
</template>

