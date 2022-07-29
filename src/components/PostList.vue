<template>
  <div class="main-container">
    <div class="post-header">
      <div class="post-header__title"><strong>"Название"</strong></div>
      <div class="post-header__href"><strong>Смотреть всё &nbsp; ></strong></div>
    </div>
    <div class="post-line">
      <div class="post-container" v-for="post in mappedItems">
        <div class="post-img" :style="post.colorObject">
          <div class="post-img__label">Скидка до 20%</div>
        </div>
        <div class="post-info">{{ post.info }}</div>
        <div class="post-name">{{ post.name }}</div>
        <div class="post-location">Ближайшее: <span class="post-location__text">{{ post.location }}</span></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'Название', color: 'tomato', info: 'Sale! Скидки до 50%!', name: 'Finn Flare', location: 'Ростов-на-Дону, Улица 1, 1 (100м)'},
        {id: 2, title: 'Название', color: 'teal', info: 'Акция "Именинники"', name: "Л'Этуаль", location: 'Ростов-на-Дону, Улица 2, 2 (200м)'},
        {id: 3, title: 'Название', color: 'blueviolet', info: 'Больше покупок - Больше баллов!', name: 'Fix Price', location: 'Ростов-на-Дону, Улица 3, 3 (300м)'},
        {id: 4, title: 'Название', color: 'yellow', info: 'Скидка 3% на монитор', name: 'МТС', location: 'Ростов-на-Дону, Улица 4, 4 (400м)'},
        {id: 5, title: 'Название', color: 'skyblue', info: 'Дачные сезоны', name: 'Hoff', location: 'Ростов-на-Дону, Улица 5, 5 (500м)'},
      ]
    }
  },
  computed: {
    mappedItems() {
      return this.posts.map(el => ({
        ...el,
        colorObject: {
          background: el.color
        }
      }))
    }
  },
}
</script>

<style scoped lang="scss">
  .main-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 10px;
  }

  .post-header {
    height: 20%;
    display: flex;
    justify-content: space-between;
  }

  .post-header__title {
    padding: 10px;
  }

  .post-header__href {
    padding: 10px;
    color: turquoise;
    cursor: pointer;
  }

  .post-line {
    padding: 10px;
    display: flex;
    white-space: nowrap;
    align-items: center;
    touch-action: manipulation;
    overflow: auto;
    -ms-overflow-style: none;

    &::-webkit-scrollbar {
      width: 0;
      height: 0;
    }
  }

  .post-container {
    display: flex;
    flex-direction: column;
    margin-right: 10px;
    height: 280px;
    min-width: 250px;
    border-radius: 8px;
    box-shadow: 0 3px 8px 2px lightgray;
  }

  .post-img {
    padding: 10px;
    height: 60%;
    width: 100%;
    border-radius: 10px;
  }

  .post-img__label {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 25px;
    width: 100px;
    background: gold;
    font-size: small;
    color: white;
    border-radius: 10px;
    transform: translate(5px, -15px);
  }

  .post-info {
    padding: 10px;
    font-size: small;
    font-weight: bold;
  }

  .post-name {
    padding: 10px 10px 0;
  }

  .post-location {
    padding: 10px;
    box-sizing: border-box;
    white-space: break-spaces;
    max-width: 80%;
    font-size: 75%;
    color: darkgray;
  }

  .post-location__text {
    color: dimgray;
  }
</style>