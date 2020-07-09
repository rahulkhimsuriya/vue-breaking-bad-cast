<template>
  <div>
    <h3
      v-for="character in characters"
      v-text="character.name"
      :key="character.char_id"
    ></h3>
  </div>
</template>

<script>
import axios from 'axios'

export default {
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
