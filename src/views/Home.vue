<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>Search Term - {{search}}</p>
    <div v-for="stack in matchingStacks" :key="stack">
      {{stack}}
    </div>
  </div>
</template>

<script>
import {computed, ref} from 'vue'
export default {
  setup(){
   const search = ref('')
   const stacks = ref(['html', 'css', 'js', 'php', 'react', 'vue', 'angular'])

   const matchingStacks = computed(() => {
     return stacks.value.filter(stack => stack.includes(search.value))
   })

    return {stacks, search, matchingStacks}
}
}
</script>

<style>

</style>