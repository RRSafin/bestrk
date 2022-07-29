<template>
  <div class="form-container">
    <form @submit.prevent>
      <input type="text" class="search-input" placeholder="Поиск по всем категориям">
    </form>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

  .form-container {
    background: white;
  }

  form {
    margin: 5px 10px 10px;
    height: 2rem;
  }

  .search-input {
    border: none;
    padding: 10px;
    height: 100%;
    width: 100%;
    background-color: #f2f2f2;
    border-radius: 5px;
    box-shadow: inset 0 0 4px gray;
  }

  .search-input::placeholder {
    color: #212529;
    opacity: 0.4;
  }
</style>