<template>
  <div id="app" class="min-h-screen bg-green-900">
    <div class="inline-block flex item-center justify-center py-6">
      <img class="w-40 h-auto" alt="Vue logo" src="./assets/image/logo.png" />
    </div>

    <div class="container mx-auto">
      <div class="flex flex-wrap justify-center md:justify-start">
        <CharacterCard
          v-for="character in characters"
          :character="character"
          :key="character.char_id"
        />
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

import CharacterCard from '@/components/CharacterCard.vue'

export default {
  name: 'App',
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
  },

  methods: {}
}
</script>

<style src="./assets/css/tailwind.css"></style>
