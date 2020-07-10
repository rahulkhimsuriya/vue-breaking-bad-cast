<template>
  <div class="w-full px-3 relative">
    <span class="absolute w-6 h-6 top-0 left-0 ml-6 mt-3 ">
      <svg
        class="text-gray-700 w-6 h-6 top-0 left-0 absolute"
        viewBox="0 0 20 20"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M12.906 14.32a8 8 0 111.414-1.414l5.337 5.337-1.414 1.414-5.337-5.337zM8 14A6 6 0 108 2a6 6 0 000 12z"
          fill="currentColor"
          fill-rule="evenodd"
        />
      </svg>
    </span>
    <input
      class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 pl-10 pr-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
      type="text"
      placeholder="Search charater by name"
      v-model="searchText"
      @keyup="searchCharacters"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchText: ''
    }
  },

  methods: {
    searchCharacters() {
      this.$emit('characterWasSearched', this.searchText)
    }
  }
}
</script>

<style lang="css" scoped></style>
