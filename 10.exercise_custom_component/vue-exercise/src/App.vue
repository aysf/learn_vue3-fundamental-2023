<script>
import BenderStatistics from './components/BenderStatistics.vue'

export default {
  components: {
    BenderStatistics,
  },
  data: () => ({
    characters: [
      {
        name: 'Aang',
        element: ['Air', 'Water', 'Earth', 'Fire']
      },
      {
        name: 'Zuko',
        element: ['Fire']
      },
      {
        name: 'Katara',
        element: ['Water']
      },
      {
        name: 'Toph',
        element: ['Earth']
      }
    ],
    favoriteList: [],
    newCharacter: {
      name: '',
      element: []
    }
  }),
  methods: {
    addNewCharacter() {
      this.characters.push(this.newCharacter)
      this.newCharacter = { name: '' }
    },
    favoriteCharacters(char) {
      this.favoriteList.push(char)
    }
  }
}
</script>

<template>
  <h1>Characters</h1>

  <!-- statistic -->
  <BenderStatistics v-bind:charactersParam="characters" />

  <h2>show characters in the paragraf</h2>
  <p>
    <span v-for="(char, idx) in characters">
      {{ char.name }}{{ idx === characters.length - 1 ? '' : ', ' }}
    </span>
  </p>

  <h2>show favorite characters</h2>
  <p v-if="favoriteList.length > 0">
    <span v-for="(char, idx) in favoriteList">
      {{ char.name }}{{ idx === favoriteList.length - 1 ? '' : ', ' }}
    </span>
  </p>
  <p v-else>no favorite Characters</p>

  <h2>add new character</h2>
  <label for="new-characters"></label>
  <input type="text" v-model="newCharacter.name" @keyup.enter="addNewCharacter" />
</template>
