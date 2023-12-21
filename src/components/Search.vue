<template>
    <div class="w-full max-w-4xl">
    <h2 class="text-xl md:text-2xl mx-3 font-semibold mb-4">Find and Aggregate Instagram UGC (User Generated Content)</h2>
    <p class="text-sm mx-3" >The data displayed below is mock data </p>
      <form @submit.prevent="search" class="mt-5 mx-3 sm:flex sm:items-center">
        <input 
          v-model="searchTerm"
          class="inline w-full rounded-md border border-gray-300 bg-white py-2 pl-3 pr-3 leading-5 placeholder-gray-500 focus:border-indigo-500 focus:placeholder-gray-400 focus:outline-none focus:ring-1 focus:ring-indigo-500 sm:text-sm" 
          placeholder="Enter hashtags(#trend...) or mentions(@user...)"
          type="search" 
          autofocus
        >
        <button 
          type="submit" 
          class="mt-3 inline-flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-4 py-2 font-medium text-white shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm"
        >
          Search
        </button>
      </form>
    </div>
</template>

<script>
export default {
  data() {
    return {
      searchTerm: "",
    };
  },
  watch: {
    // Watch for changes in searchTerm
    searchTerm(newVal) {
      // Emit an event whenever searchTerm changes
      this.$emit('search-update', newVal);
    },
  },
  methods: {
    search() {
      this.$emit('search-update', this.searchTerm);
    },
  },
};
</script>

<style scoped>
/* Tailwind handles most styling, so additional styles might not be needed */
</style>
