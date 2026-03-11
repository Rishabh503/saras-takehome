<script setup></script>
<template>
    <div>
        <div v-for="i in 5" :key="i"
        class="border border-green-50  animate-pulse shadow-sm mb-4 mt-2 p-2 bg-white rounded-lg"
        >
            <div class="flex  justify-between mb-4">
                <div class="w-2/3">
                    <div class="h-5 bg-gray-200 rounded mb-2 w-3/4"></div>
                    <div class="h-5 bg-gray-200 rounded mb-2 w-1/2"></div>
                    <div>
                        <div class="h-5 bg-gray-200 rounded mt-4 -mb-2 w-1/3"></div>
                    </div>

                </div>
                <div class="flex justify-between flex-col">
                  <div  class="flex justify-end  gap-2">
                      <div class="w-14 h-4 bg-gray-200 rounded">

                    </div>
                    <div class="w-14 h-4 bg-gray-200 rounded">

                    </div>
                  </div>
                  <div class="w-32 h-4  flex justify-end   bg-gray-200 rounded">

                  </div>
                    
                </div>
                
            </div>
        </div>
    </div>
</template>