<template>
  <div class="content">
    <h1>Refs vs Reactive</h1>
    <!-- Refs vs Reactive -->
    <h2>Refs</h2>
    <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update ninja one</button>
    <h2>Reactive</h2>
    <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Update ninja two</button>
    <p></p>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';

export default {
  name: 'RefsVsReactive',
  setup() {
    const ninjaOne = ref({ name: 'mario', age: 30 })
    const ninjaTwo = reactive({ name: 'luigi', age: 35 })
  
  // NOTE: We can't use primitive value in Reactive

    const updateNinjaOne = () => {
      ninjaOne.value.age = 40
    }
   
    const updateNinjaTwo = () => {
      // One of the major difference is you don't have to use dot notation 'value' then the 'key'
      ninjaTwo.age = 40
    }


    return { ninjaOne, updateNinjaOne, updateNinjaTwo, ninjaTwo }
  } 
}
</script>

<style>

</style>