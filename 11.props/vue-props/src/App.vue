<script>
import BaseCounter from './components/base-counter.vue'
import UserCard from './components/user-card.vue'

export default {
    data() {
        return {
            message: 'Hello from vue!!',
            listOfNumber: [1, 2, 3, 4],
            userData: {
              name: "Ben",
              preferredFramework: "vue",
              favoriteFood: "egg",
              favoriteNumber: [3,4,5],
            }
        };
    },
    watch: {
        count(newValue) {
            if (newValue > 20) {
                this.countTitle += ' very big';
            }
        }
    },
    computed: {
        displayTitle() {
            if (this.count > 20) {
                return 'Count Standard Very Long';
            }
            else {
                return 'Count Standard';
            }
        },
        refinedUserData() {
          return {
            name: this.userData.name,
            food: this.userData.favoriteFood,
          }
        }
    },
    components: { BaseCounter, UserCard }
}
</script>

<template>

  <UserCard :user="refinedUserData" />

  <h1>if/else directive</h1>
  <p v-if="message.length % 2 === 0">Even: {{ message.toUpperCase() }}</p>
  <p v-else>Odd: {{ message }}</p>

  <h1>list directive</h1>
  <ul>
    <li v-for="num in listOfNumber">{{ num * Math.random() }}</li>
  </ul>

  <BaseCounter />

</template>
