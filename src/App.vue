<template>
  <div class="app">
    <div class="container">
      <Navbar />
      <PostList />
      <PostList />
      <PostList />
      <PostList />
      <PostList />
    </div>
  </div>
</template>

<script>

import Navbar from "@/components/Navbar";
import PostList from "@/components/PostList";

export default {
  components: {Navbar, PostList},

  data() {

  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  min-height: 700px;
  max-width: 440px;
  min-width: 320px;
  background: snow;
}
</style>