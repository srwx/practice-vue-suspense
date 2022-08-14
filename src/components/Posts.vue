<template>
  <div v-for="post in posts" :key="post.id">
    {{ console.log(post) }}
    {{ post.title }}
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "PostsComponent",

  // Adding the below computed properties in your Vue component will allow {{ console.log }} within the <template>.
  computed: {
    console: () => console,
    window: () => window,
  },

  async setup() {
    const posts = ref();
    const res = await fetch("https://jsonplaceholder.typicode.com/posts");
    posts.value = await res.json();
    return { posts };
  },
};
</script>
