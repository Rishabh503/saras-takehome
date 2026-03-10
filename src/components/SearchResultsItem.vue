<script setup>
import { ref } from "vue"
import {  ArrowRight,X } from "lucide-vue-next"
    const props=defineProps({
        title:String,
        desc:String,
        language:String,
        releaseDate:String,
        genres:Array
    })
// :key="item.show.id"
//       :title="item.show.name"
//       :desc="item.show.summary"
//       :language="item.show.language"
//       :releaseDate="item.show.premiered"

const isOpen = ref(false)
const open=ref("Read More...")

function toggle() {
  isOpen.value = !isOpen.value
    if(isOpen.value){
        open.value=''
    }else open.value="Read More..."
}
</script>

<template>
  <div class="border border-green-50 rounded-lg bg-white p-4 shadow-sm hover:shadow-md transition mb-4">
    
   <div class="flex justify-between">
     <div>
        <h2 class="text-lg font-semibold mb-2">
      {{ title }}
    </h2>

    <p class="text-gray-600 mb-3">
      Date of Release : {{ releaseDate }}
    </p>
  
     </div>
    <div v-if="genres && genres.length" >
  <span
    v-for="genre in genres"
    :key="genre"
    class="text-xs bg-green-100 mx-2 text-green-700 px-2  py-1 rounded"
  >
    {{ genre }}
  </span>
</div>
    <div v-if="genres && genres.length==0" >
  <span
    class="text-xs bg-green-100 mx-2 text-red-700 px-2  py-1 rounded"
  >
    Genre Not Available 
  </span>
</div>
   </div>
   

    <div class="cursor-pointer flex items-center justify-between font-bold" @click="toggle">
    <span class="text-sm text-green-600 font-medium">
      Language: {{ language }}
    </span>
       <span v-if="open === ''">
  <X class="w-4 h-4"/>
</span>
<span v-else>
  {{ open }}
</span>
    </div>

    <div v-if="isOpen" class="mt-3  text-gray-600">
    <!-- {{desc}} -->
       <p v-html="desc"></p>
    </div>

  </div>
</template>