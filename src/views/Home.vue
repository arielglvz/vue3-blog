<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle post</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from '@/components/PostList.vue';
import { ref } from 'vue';
export default {
  name: 'Home',
  components: { PostList },
  setup() {
    const posts = ref([
      { title: 'welcome to the blog', body: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem, at! Est quibusdam debitis itaque quisquam, recusandae natus dolore quae ullam voluptas ad aliquid quasi dolorum doloremque sapiente placeat ut. Animi optio quam quis ipsum quas consequatur veniam quod dolorem amet, quo, inventore voluptatem id expedita minus dolore architecto harum magni sit illo voluptatibus pariatur. Voluptates deleniti culpa error qui distinctio, eos ex necessitatibus, id atque aliquam maiores, iste laborum doloribus suscipit officiis accusamus magni! Iure, beatae deleniti earum ipsa omnis minima, exercitationem fuga neque rerum quidem iste libero tempora quisquam velit quaerat maxime modi qui, natus in mollitia magnam. Facere?', id: 1 },
      { title: 'top 5 css tips', body: 'Lorem ipsum', id: 2 },
    ])

    const showPosts = ref(true)

    return { posts, showPosts }
  }
}
</script>

<style>

</style>