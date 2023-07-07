<template>
  <BaseLayout>
    <template v-slot:header><h1>Let's do this!</h1></template>
    <template v-slot:sidebar> Sidebar </template>
    <template v-slot:main>
      <FavoriteCharacters :characters="characters" />
      <AddCharacters @character-added="handleCharacterAdded" />
      <FavoriteMoments />
      <Statistics :characters="characters" />
      <ShotLocations @addLocation="handleNewLocation" :locations="shotLocations" />
    </template>
    <template v-slot:footer>Copyright Tom Kline</template>
  </BaseLayout>
</template>

<script>
import FavoriteCharacters from './components/FavoriteCharacters.vue'
import AddCharacters from './components/AddCharacters.vue'
import FavoriteMoments from './components/FavoriteMoments.vue'
import Statistics from './components/Statistics.vue'
import ShotLocations from './components/ShotLocations.vue'
import BaseLayout from './components/BaseLayout.vue'

export default {
  components: {
    FavoriteCharacters,
    AddCharacters,
    FavoriteMoments,
    Statistics,
    ShotLocations,
    BaseLayout
  },
  data() {
    return {
      characters: [
        {
          name: 'Tom Wambsgams',
          personality: 'Worrisome',
          affiliation: 'Logan',
          netWorth: 15000000
        },
        {
          name: 'Shiv Roy',
          personality: 'Hypocrite',
          affiliation: 'Self',
          netWorth: 200000000
        },
        {
          name: 'Roman Roy',
          personality: 'Facist',
          affiliation: 'Self',
          netWorth: 150000000
        },
        {
          name: 'Kendall Roy',
          personality: 'Narcissist',
          affiliation: 'Self',
          netWorth: 350000000
        }
      ],
      shotLocations: ['Caumsett']
    }
  },
  methods: {
    handleCharacterAdded(newCharacter) {
      this.characters.push(newCharacter)
    },
    handleNewLocation(newLocation) {
      this.shotLocations.push(newLocation)
    }
  }
}
</script>
