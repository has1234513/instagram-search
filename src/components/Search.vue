<template>
  <div class="bg-white p-4 md:p-6 rounded-lg shadow-lg">
    <h2 class="text-xl md:text-2xl font-semibold mb-4">Find and Aggregate Instagram UGC (User Generated Content)</h2>
    <div class="relative rounded-full border border-gray-300 p-3">
      <input
        v-model="searchTerm"
        class="w-full outline-none placeholder-gray-500"
        type="text"
        placeholder="Enter hashtags(#trend...) or mentions(@user...)"
      />
      <button
        @click="search"
        class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-blue-500 text-white px-4 py-2 md:px-6 md:py-3 rounded-full hover:bg-blue-600 text-sm md:text-base">
        Search 
      <font-awesome-icon icon="fa-solid fa-magnifying-glass" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchTerm: "",
    };
  },
  methods: {
    search() {
      // Implement search functionality here
    },
  },
};
</script>

<style scoped>
/* Tailwind handles most styling, so additional styles might not be needed */
</style>
