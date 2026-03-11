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
  // validating if the user query is there or not  
  if(!query){
    results.value=[];
    return
  }
// setting up the values for a new search
     loading.value=true;
     emptyResponse.value=false
     results.value=[]


  try {
     const res = await fetch(`https://api.tvmaze.com/search/shows?q=${query}`)
    const data = await res.json()
    // adding the data to the results
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
  <div class="min-h-screen bg-[#fdf9f9] flex justify-center sm:px-6   p-6">
    <div class="w-full px-1 sm:px-0   max-w-3xl mx-auto">
      <h1 class="text-xl sm:text-3xl md:text-4xl
        font-bold text-[#11d493] m-6 text-center">
        Which Movie Are You Looking for?</h1>
      <p class="text-center px-2 text-gray-500 text-sm sm:text-base ">
        Type your query and get the best results out there in just one click !!
      </p>
      <SearchBar @search="search" />
      <Loader v-if="loading"/>
    <!-- <Loader/> -->
<div class="mt-4">
        <SearchResultList :results="results" :emptyResponse="emptyResponse"/>
</div>
    </div>
    
  </div>
</template>