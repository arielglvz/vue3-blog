<template>
  <div class="content">
    <h1>watch vs watchEffect </h1>
    <input type="text" v-model="search">
    <p>Search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
    <button @click="handleStopWatching">stop watching</button>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from 'vue';

export default {
  name: 'WatchVsWatchEffect',
  setup() {
    const search = ref('')
    const names = ref(['mario', 'yoshi', 'luigi', 'toad',  'bowser', 'koopa', 'peach',])

    /** 
     * ! watch vs watchEffect 
     * TODO: Use watch when you need fine-grained control over which dependencies trigger the side effect. 
     * TODO: Use watchEffect for automatic, comprehensive tracking of all reactive dependencies within a function.
    */

    /** 
     * * How to stop watching. Simply store it into a variable 
    */
    const stopWatching = watch(search, () => {
      console.log('watch function run')
    })

    const stopEffect = watchEffect(() => {
      console.log('watchEffect function run', search.value)
    })

    /** 
     * ! Computed Values
    */
    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    /** 
     * ! Handle stop watching
    */
    const handleStopWatching = () => {
      stopWatching()
      stopEffect()
    }

    return { names, search, matchingNames, handleStopWatching}
  }
}
</script>

<style>

</style>