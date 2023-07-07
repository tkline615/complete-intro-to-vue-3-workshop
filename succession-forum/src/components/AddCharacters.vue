<template>
  <div>
    <h2>Add New Character</h2>
    <form @submit="handleSubmit">
      <label for="name">Name:</label>
      <input type="text" name="name" />

      <label for="personality">Personality:</label>
      <input type="text" name="personality" />

      <label for="affiliation">Affiliation</label>
      <input type="text" name="affiliation" />

      <br />
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  // theres no need for prop here, we don't need to know about the characters array in order to let
  // the parent component know that we're modifying it
  //   props: {
  //     characters: Array
  //   },
  methods: {
    addToCharacters(name, personality, affiliation) {
      //   this.characters.push({ name: name, personality: personality, affiliation: affiliation })
      // emit the event to notify the parent
      this.$emit('character-added', { name, personality, affiliation })
    },
    handleSubmit(event) {
      event.preventDefault() // Prevent the default form submission
      console.log(event)
      console.log(`Name is: ${event.target.name.value}`)
      this.addToCharacters(
        event.target.name.value,
        event.target.personality.value,
        event.target.affiliation.value
      )
    }
  }
}
</script>
