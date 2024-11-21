<template>
  <div class="home">
    home
    <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  // Composition API:
  setup() {
    let name = 'Mario'
    let age = 30

    const handleClick = () => {
      console.log('You clicked me')
    }
    return { name, age, handleClick}
  },
}
</script>
