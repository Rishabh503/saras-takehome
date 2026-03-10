<script setup>
import { ref } from "vue"
import ListItem from "./SearchResultsItem.vue"

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
  <div class="mt-2">

    <ListItem
      v-for="item in items"
      :key="item.id"
      :title="item.title"
      :desc="item.desc"
      :source="item.source"
      :extra="item.extra"
    />

  </div>
</template>