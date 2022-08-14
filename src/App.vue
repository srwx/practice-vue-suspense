<template>
  <div id="app">
    <Suspense>
      <template #default>
        <Posts />
      </template>
      <template #fallback>
        <p>Loading...</p>
      </template>
    </Suspense>
  </div>
</template>

<script>
import Posts from "./components/Posts.vue";
import { Suspense } from "vue";

export default {
  name: "App",
  components: {
    Posts,
    Suspense,
  },
};
</script>
