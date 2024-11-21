<template>
  <div class="templateRefs">
    Test
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name"/>
  </div>
</template>

<script>
import { ref } from 'vue';

// @ is an alias to /src

export default {
  name: 'TemplateRefs',

  // Composition API:
  setup() {
    
    // Using Refs for reactivity
    const name = ref('Mario')
    const age = ref(30)

    const handleClick = () => {
      name.value = 'luigi'
      age.value = 35
    }

    return { name, age, handleClick }
  },
}
</script>
