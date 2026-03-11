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


const isOpen = ref(false)
const open=ref("Read More..")

function toggle() {
  isOpen.value = !isOpen.value
    if(isOpen.value){
        open.value=''
    }else open.value="Read More.."
}
</script>

<template>
  <div @click="toggle"  class="border border-green-50 rounded-lg bg-white p-4 shadow-sm hover:shadow-md cursor-pointer transition mb-4">
    
   <div class="flex flex-col  sm:justify-between  sm:flex-row sm:items-start gap-2 ">
     <div>
        <h2 class="text-base font-semibold mb-2 sm:text-lg ">
      {{ title }}
    </h2>

    <p class="text-gray-600 mb-3">
      Date of Release : {{ releaseDate }}
    </p>
  
     </div>
    <div v-if="genres && genres.length" 
    class="flex  flex-wrap mt-1 sm:mt-0"
    >
  <span
    v-for="genre in genres"
    :key="genre"
    class="text-xs bg-green-100 mr-2 mb-1 text-green-700 px-2  py-1 rounded"
  >
    {{ genre }}
  </span>
</div>
    <div v-if="genres && genres.length==0" 
     class="flex  flex-wrap mt-1 sm:mt-0"
    >
  <span
    class="text-xs bg-green-100 mr-2 mb-1 text-red-700 px-2  py-1 rounded"
  >
    Genre Not Available 
  </span>
</div>
   </div>
   

    <div class="cursor-pointer sm:p-0 px-0.5 flex items-center justify-between font-bold"  >
    <span class="text-sm text-green-600 font-medium">
      Language: {{ language }}
    </span>
      
    </div>

    <transition name="fade">
        <div v-if="isOpen" class="mt-3 sm:text-base text-sm   text-gray-600">
        <!-- {{desc}} -->
          <p v-html="desc"></p>
        </div>

    </transition>
  </div>
</template>


<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition:all 0.25s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform:translateY(-6px);
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
  transform:translateY(0);
}
</style>