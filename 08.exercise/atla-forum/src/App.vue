<script>
export default {
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

      this.characters.forEach((char) => {
        elements.forEach((element) => {
          if (char.element.indexOf(element) > -1) {
            statistics[element] += 1
          }
        })
      })

      return statistics
    }
  },
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

  <h2>Statistics</h2>
  <ul></ul>
  {{ benderStatistics }}

  <h2>show characters in the list</h2>
  <ul>
    <li v-for="char in characters">
      <p>{{ char.name }}</p>
      <button @click="favoriteCharacters(char)">⭐ Favorite</button>
    </li>
  </ul>

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
