<script setup>
import { ref } from "vue"
import ListItem from "./SearchResultsItem.vue"

const props = defineProps({
  results: {
    type: Array,
    default: () => []
  },
  emptyResponse:Boolean
})
console.log(props.results)
if(props.results){
    console.log("from props",props.results.length)
}

const items = ref([
  {
    id: 1,
    title: "Vue 3 Composition API",
    desc: "A modern way to write Vue components with better logic reuse.",
    source: "Vue Docs",
    extra:"lorem ispo donor today is the baady doso os oeuo wloo donor is the wen f ojosn sjao in todys worldisis usuoa hbjosow hbxisouw s osh"
  },
  {
    id: 2,
    title: "Understanding Reactivity",
    desc: "Vue's reactivity system tracks dependencies automatically.",
    source: "Vue Guide",
    extra:"lorem ispo donor today is the baady doso os oeuo wloo donor is the wen f ojosn sjao in todys worldisis usuoa hbjosow hbxisouw s osh"
  },
  {
    id: 3,
    title: "Component Based Architecture",
    desc: "Breaking UI into reusable components improves maintainability.",
    source: "Frontend Handbook",
    extra:"lorem ispo donor today is the baady doso os oeuo wloo donor is the wen f ojosn sjao in todys worldisis usuoa hbjosow hbxisouw s osh"
  }
])

</script>

<template>
  <div v-if="!emptyResponse" class="mt-2">

    <ListItem
      v-for="item in props.results"
      :key="item.show.id"
      :title="item.show.name"
      :desc="item.show.summary"
      :language="item.show.language"
      :releaseDate="item.show.premiered"
      :genres="item.show.genres"
    />

  </div>

  <div v-else  class="border border-green-50 shadow-sm mb-4 mt-2 p-3 bg-white rounded-lg">
  <p class="text-sm text-gray-700">
    No results found for your search.  
    Try searching for something like <span class="font-medium">cricket</span>, 
    <span class="font-medium">batman</span>, 
    <span class="font-medium">dogs</span>, or 
    <span class="font-medium">dance</span>.
  </p>

  <p class="text-xs text-gray-500 mt-1">
    It’s also possible the search term is invalid or not available in our dataset.
  </p>
</div>
</template>