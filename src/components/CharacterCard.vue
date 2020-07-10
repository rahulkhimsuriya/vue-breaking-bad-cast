<template>
  <div class="max-w-sm md:w-1/3 lg:w-1/5 w-full px-4 mb-10 overflow-hidden">
    <div class="rounded overflow-hidden relative shadow-lg">
      <img
        class="w-full object-fit"
        :class="{ 'opacity-75': isActive }"
        style="height:350px;"
        :src="character.img"
        :alt="character.nickname"
      />

      <button
        class="absolute tex-white top-0 right-0 m-4 focus:outline-none"
        @click="isActive = !isActive"
      >
        <svg
          class="h-6 w-6 text-white"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M1 1h18v2H1V1zm0 8h18v2H1V9zm0 8h18v2H1v-2zM7 5h12v2H7V5zm0 8h12v2H7v-2z"
            fill="currentColor"
            fill-rule="evenodd"
          />
        </svg>
      </button>

      <div class="character-info p-4 bg-gray-100 text-center absolute w-full">
        <h3 class="text-xl text-gray-800 font-semibold">
          {{ character.name }}
        </h3>
        <h5 class="text-md text-gray-600 font-bold leading-loose">
          {{ character.nickname }}
        </h5>

        <ul class="-mx-4 text-sm text-left" v-show="isActive">
          <li class="border-t border-gray-600 p-2 flex justify-between">
            <span class="font-bold text-gray-800 mr-2">ID</span>
            <span>{{ character.char_id }}</span>
          </li>
          <li class="border-t border-gray-600 p-2 flex justify-between">
            <span class="font-bold text-gray-800 mr-2">Occupation</span>
            <span>{{ occupation }}</span>
          </li>
          <li class="border-t border-gray-600 p-2 flex justify-between">
            <span class="font-bold text-gray-800 mr-2">Seasons</span>
            <span>{{ appearanceInSeasons }}</span>
          </li>
          <li class="border-t border-gray-600 p-2 flex justify-between">
            <span class="font-bold text-gray-800 mr-2">
              Status (Death/Alive)
            </span>
            <span>{{ character.status }}</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    character: {
      required: true
    }
  },

  data() {
    return {
      isActive: false
    }
  },

  computed: {
    occupation() {
      return this.character.occupation.join(', ')
    },

    appearanceInSeasons() {
      return this.character.appearance.join(', ')
    }
  }
}
</script>

<style scoped>
.character-info {
  bottom: 0px;
  width: 100%;
}
</style>
