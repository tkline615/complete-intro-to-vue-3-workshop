<template>
  <h2>Shot Locations</h2>
  <pre>{{ locations }}</pre>
  <label for="addLocation">Add Location: </label>
  <input type="text" name="addLocation" v-model="newLocation" />
  <br />
  <button @click="handleNewLocation">Submit:</button>
</template>

<script>
export default {
  data() {
    return {
      newLocation: ''
    }
  },
  props: {
    locations: Array
  },
  emits: ['addLocation'],
  methods: {
    handleNewLocation() {
      console.log(`${this.newLocation}`)
      this.$emit('addLocation', this.newLocation)
    }
  }
}
</script>
