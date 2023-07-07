<template>
  <div>
    <h2>Statistics</h2>
    <ul>
      <li>Number of characters loyal to Logan: {{ calculateLoyalCharacters }}</li>
      <li>Number of characters disloyal to Logan: {{ calculateDisloyalCharacters }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  props: {
    characters: Array
  },
  computed: {
    calculateLoyalCharacters() {
      const loyalCharacters = this.characters.filter((character) => {
        return character.affiliation === 'Logan'
      })
      return loyalCharacters.length
    },
    calculateDisloyalCharacters() {
      const disloyalCharacters = this.characters.filter((character) => {
        return character.affiliation != 'Logan'
      })
      return disloyalCharacters.length
    }
  }
}
</script>
