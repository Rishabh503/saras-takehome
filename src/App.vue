<script setup>
import SearchBar from './components/SearchBar.vue'
import SearchResultList from './components/SearchResultList.vue'
import Loader from './components/Loader.vue'
import {ref} from "vue"
// const show=ref(false)
const results=ref([]);
const loading = ref(false)
const emptyResponse=ref(false)

async function search(query){
  if(!query){
    results.value=[];
    return
  }
  loading.value=true;
  try {
     const res = await fetch(`https://api.tvmaze.com/search/shows?q=${query}`)
    const data = await res.json()

    results.value = data
    if(data.length==0){
      emptyResponse.value=true;
    }else{
      emptyResponse.value=false
    }
    // console.log(results.value)
  } catch (error) {
    console.log("error from vue.app:",error)
  }

  loading.value=false;
}
</script>

<template>
  <div class="min-h-screen bg-[#fdf9f9] flex justify-center   p-6">
    <div class="w-full max-w-3xl mx-auto">
      <h1 class="text-4xl font-bold text-[#11d493] m-6 text-center">What Are You Looking for?</h1>
      <p class="text-center text-gray-500">
        Type your query and get the best results out there in just one click !!
      </p>
      <SearchBar @search="search" />
      <Loader v-if="loading"/>
    <!-- <Loader/> -->
      <SearchResultList :results="results" :emptyResponse="emptyResponse"/>
    </div>
    
  </div>
</template>