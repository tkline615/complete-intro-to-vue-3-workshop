<template>
  <ul v-if="characters.length > 0">
    <li v-for="(character, index) in characters" :key="`character-${index}`">
      {{ character.name }} is {{ determineAffiliation(character) }}. Mark as favorite:
      <button v-if="!isFavorite(character)" v-on:click="addToFavorites(character)">Favorite</button>
    </li>
  </ul>
  <p v-else>Characters array is empty.</p>

  <h2>Favorites</h2>
  <div v-if="favoriteCharacters.length > 0">
    <ul>
      <li v-for="(favorite, index) in favoriteCharacters" :key="`favoriteCharacter-${index}`">
        {{ favorite.name }}
      </li>
    </ul>
  </div>
  <div v-else><p>Nobody is a favorite yet.</p></div>
</template>

<script>
export default {
  data() {
    return {
      favoriteCharacters: []
    }
  },
  methods: {
    determineAffiliation(character) {
      return character.affiliation === 'Self' ? 'Disloyal' : 'Loyal'
    },
    addToFavorites(character) {
      console.log(character)
      this.favoriteCharacters.push(character)
    },
    isFavorite(character) {
      return this.favoriteCharacters.includes(character)
    }
  },
  props: {
    characters: Array
  }
}
</script>
