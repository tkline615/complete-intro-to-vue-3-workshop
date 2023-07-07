<template>
  <div>
    <h2>Favorite Moments</h2>
    <pre> {{ favoriteMoment }}</pre>
    <label for="favoriteMoment">Favorite Moment</label>
    <input type="text" name="favoriteMoment" v-model="favoriteMoment.details" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      favoriteMoment: {
        details: ''
      }
    }
  }
}
</script>
