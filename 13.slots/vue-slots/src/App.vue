<script>
import BaseButton from './components/BaseButton.vue'
import BaseCounter from './components/BaseCounter.vue'
import BaseLayout from './components/BaseLayout.vue'
import UserCard from './components/UserCard.vue'

export default {
  data() {
    return {
      message: 'Hello from vue!!',
      listOfNumber: [1, 2, 3, 4],
      user: {
        name: 'John',
        email: 'john@mail.com',
        favFood: 'pancake'
      }
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
    refindedData() {
      return {
        name: this.user.name,
        food: this.user.favFood,
      }
    },
  },
  components: { BaseCounter, UserCard, BaseButton, BaseLayout }
}
</script>

<template>
  <h1>User Card</h1>
  <UserCard v-bind:userProps="refindedData" />

  <h1>if/else directive</h1>
  <p v-if="message.length % 2 === 0">Even: {{ message.toUpperCase() }}</p>
  <p v-else>Odd: {{ message }}</p>

  <h1>list directive</h1>
  <ul>
    <li v-for="num in listOfNumber">{{ num * Math.random() }}</li>
  </ul>

  <BaseCounter />

  
  <BaseButton isShortButton="true" />

  <BaseLayout>
    <template v-slot:aside>This is custom aside content</template>
    <template v-slot:main>This is custom main content</template>
    <template v-slot:footer>This is custom footer content</template>
  </BaseLayout>

</template>
