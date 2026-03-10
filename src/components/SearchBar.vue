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
        <div class="w-full flex items-center rounded-xl mt-4 shadow-sm pl-4 border-green-200 bg-white ">
            <Search class="mr-2 text-gray-300 w-5 h-5"/>
            <input type="text" v-model="query" placeholder="Start typing your query here "
            class="flex-1 text-gray-600 placeholder-gray-400 outline-none"
            />
        <button @click="onSearch"
      class="ml-3 bg-green-400 hover:bg-green-500 text-white p-2 rounded-lg flex items-center justify-center"
    >
        <ArrowRight class="h-4"/>
    </button>
        </div>
    </main>
   
</template>

<style scoped>
</style>
