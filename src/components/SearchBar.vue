<script setup>
import {ref} from "vue"

import { Search, ArrowRight } from "lucide-vue-next"
const query=ref("")
const emit=defineEmits(["search"])
function onSearch(){
    console.log("query is :" , query.value)
    emit("search",query.value)
}
</script>

<template>
    <main>
        <div class="w-full flex items-center rounded-xl mt-4 shadow-sm pl-4   sm:px-4 py-2 border-green-200 bg-white ">
            <Search class="mr-2 text-gray-300 w-6 h-6"/>
            <input type="text" v-model="query" placeholder="Start typing your query here "
            class="flex-1 text-sm  sm:text-base text-gray-600 placeholder-gray-400 outline-none"
            />
        <button @click="onSearch"
      class="ml-3 mr-2 sm:mr-0 bg-green-400 hover:bg-green-500 text-white p-2 rounded-lg flex items-center justify-center"
    >
        <ArrowRight class="h-4"/>
    </button>
        </div>
    </main>
    <div v-if="query.length==0" class="w-full flex items-center justify-center gap-4 ">
      <span class="rounded-xl py-1  w-auto mt-4 shadow-sm px-4 border-green-200 bg-white ">
        Cricket
      </span>
      <span class="rounded-xl py-1  w-auto mt-4 shadow-sm px-4 border-green-200 bg-white ">
        Batman
      </span>
      <span class="rounded-xl py-1  w-auto mt-4 shadow-sm px-4 border-green-200 bg-white ">
        Dance
      </span>
      <span class="rounded-xl py-1  w-auto mt-4 shadow-sm px-4 border-green-200 bg-white ">
        Music
      </span>
    </div>
   
</template>

<style scoped>
</style>
