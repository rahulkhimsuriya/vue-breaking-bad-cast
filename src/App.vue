<template>
  <div id="app" class="min-h-screen bg-green-900">
    <div class="inline-block flex item-center justify-center py-6">
      <img class="w-40 h-auto" alt="Vue logo" src="./assets/image/logo.png" />
    </div>

    <div class="container mx-auto mt-8">
      <CharacterList></CharacterList>
    </div>
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
