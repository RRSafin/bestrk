<template>
  <div class="navbar">
    <Search />
    <Bar />
  </div>
</template>

<script>
import Search from "@/components/UI/Search";
import Bar from "@/components/UI/Bar";
export default {
  components: {Search, Bar},

}
</script>

<style scoped>
  .navbar {
    display: flex;
    flex-direction: column;
    position: sticky;
    top: 0;
    z-index: 1;
  }
</style>