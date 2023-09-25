<script>
import BaseCounter from './components/BaseCounter.vue';

export default {
    data() {
        return {
            message: 'Hello from vue!!',
            listOfNumber: [1, 2, 3, 4]
        };
    },
    components: { BaseCounter }
}
</script>

<template>
  <BaseCounter/>

  <h1>if/else directive</h1>
  <p v-if="message.length % 2 === 0">Even: {{ message.toUpperCase() }}</p>
  <p v-else>Odd: {{ message }}</p>

  <h1>list directive</h1>
  <ul>
    <li v-for="num in listOfNumber">{{ num * Math.random() }}</li>
  </ul>

</template>
