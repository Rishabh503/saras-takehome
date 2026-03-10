<script setup>
import SearchBar from './components/SearchBar.vue'
</script>

<template>
  <div class="min-h-screen bg-[#fdf9f9] flex justify-center  p-6">
    <div class="w-full max-w-3xl mx-auto">
      <h1 class="text-4xl font-bold text-[#11d493] m-6 text-center">What are You Looking for?</h1>
      <p class="text-center text-gray-500">
        Type your query and get the best results out there in just one click !!
      </p>
      <SearchBar />
    </div>
    
  </div>
</template>