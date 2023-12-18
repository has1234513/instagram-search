<script setup>
  import Search from '../components/Search.vue'
</script>

<template>
  <div class="font-sans text-black h-screen bg-white pt-20 flex flex-col items-center">
    <Search/>
    <!-- Content Display Area -->
    <div class="w-full max-w-4xl mt-8 px-4 flex justify-center">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
        <!-- Dynamic content goes here -->
        <!-- Example: -->
        <div class="bg-gray-200 p-4 w-60 rounded-lg shadow">
          <p>Content 1</p>
        </div>
        <div class="bg-gray-200 p-4 w-60 rounded-lg shadow">
          <p>Content 2</p>
        </div>
        <!-- ... more content blocks -->
      </div>
    </div>
  </div>
</template>