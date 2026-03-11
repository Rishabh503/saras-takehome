<script setup>
import {ref} from "vue"

import { Search, ArrowRight } from "lucide-vue-next"
const query=ref("")
const tags=ref([
  "Cricket","Dance","Aliens","Music"
])
const emit=defineEmits(["search"])

let debounceTimer=null;
function onSearch(){
  clearTimeout(debounceTimer)
  debounceTimer=setTimeout(()=>{
      console.log("query is :" , query.value)
    emit("search",query.value)
  },400)
  
}
</script>

<template>
    <main>
        <div class="w-full flex items-center rounded-xl mt-4 shadow-sm pl-4   sm:px-4 py-2 border-green-200 bg-white ">
            <Search class="mr-2 text-gray-300 w-6 h-6"/>
            <input type="text" v-model="query"  @input="onSearch" placeholder="Start typing your query here "
            class="flex-1 text-sm  sm:text-base text-gray-600 placeholder-gray-400 outline-none"
            />
        <!-- <button @click="onSearch"
      class="ml-3 mr-2 sm:mr-0 bg-green-400 hover:bg-green-500 text-white p-2 rounded-lg flex items-center justify-center"
    >
        <ArrowRight class="h-4"/>
    </button> -->
        </div>
    </main>
    <div v-if="query.length==0">
    <ul  class="w-full flex items-center justify-center gap-4 mt-5">
      <li v-for="tag in tags" :key="task">
        <span  @click="query=tag; onSearch()"
        class=" py-1 text-sm rounded-full  w-auto mt-4 shadow-sm px-4 border-gray-200 bg-white hover:bg-green-100   hover:scale-150 hover:border-green-300 cursor-pointer transition">
          {{ tag }}
        </span>
      </li>
    </ul>
    </div>

   
</template>

<style scoped>
</style>
