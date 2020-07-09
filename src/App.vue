<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />

    <CharacterList></CharacterList>
  </div>
</template>

<script>
import CharacterList from '@/components/CharacterList.vue'

export default {
  name: 'App',
  components: { CharacterList }
}
</script>

<style src="./assets/css/tailwind.css"></style>
