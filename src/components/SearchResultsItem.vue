<script setup>
import { ref } from "vue"
import {  ArrowRight,X } from "lucide-vue-next"
    const props=defineProps({
        title:String,
        desc:String,
        source:String,
        extra:String
    })


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
    
    <h2 class="text-lg font-semibold mb-2">
      {{ title }}
    </h2>

    <p class="text-gray-600 mb-3">
      {{ desc }}
    </p>

    <div class="cursor-pointer flex items-center justify-between font-bold" @click="toggle">
    <span class="text-sm text-green-600 font-medium">
      Source: {{ source }}
    </span>
       <span v-if="open === ''">
  <X class="w-4 h-4"/>
</span>
<span v-else>
  {{ open }}
</span>
    </div>

    <div v-if="isOpen" class="mt-3  text-gray-600">
    {{extra}}
    </div>

  </div>
</template>