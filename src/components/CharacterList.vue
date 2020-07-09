<template>
  <div class="flex flex-wrap justify-center md:justify-start">
    <CharacterCard
      v-for="character in characters"
      :character="character"
      :key="character.char_id"
    />
  </div>
</template>

<script>
import axios from 'axios'

import CharacterCard from '@/components/CharacterCard.vue'

export default {
  components: { CharacterCard },

  data() {
    return {
      characters: []
    }
  },

  created() {
    axios
      .get('https://breakingbadapi.com/api/characters')
      .then(({ data }) => (this.characters = data))
      .catch(err => console.log(err))
  }
}
</script>

<style scoped></style>
