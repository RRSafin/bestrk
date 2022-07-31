<template>
  <transition name="fade">
    <div v-if="isBarShowed" class="bar">
      <div class="bar-btn" v-for="button in buttons">
        <div class="bar-btn__icon"></div>
        <div class="bar-btn__text">{{ button.title }}</div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      isBarShowed: true,
      oldScrollY: 0,
      buttons: [
        {id: 1, title: 'Подборки'},
        {id: 2, title: 'Все категории'},
        {id: 3, title: 'Где поесть'},
        {id: 4, title: 'Техника'},
        {id: 5, title: 'Одежда'},
        {id: 6, title: 'Мебель'},
        {id: 7, title: 'Косметика'},
        {id: 8, title: 'Скидки'}
      ]
    }
  },

  mounted() {
    window.addEventListener('scroll', () => {
      const scrolled = window.scrollY;
      console.log(scrolled)

      this.isBarShowed = scrolled <= 50 || scrolled > this.oldScrollY;

      this.oldScrollY = scrolled;
    })
  }
}
</script>

<style scoped lang="scss">
  .bar {
    padding: 10px;
    display: flex;
    flex-wrap: nowrap;
    align-items: center;
    background: white;
    touch-action: pan-x;
    overflow: auto;
    -ms-overflow-style: none;
    transition: all .3s ease;

  &::-webkit-scrollbar {
     width: 0;
     height: 0;
   }
  }

  .bar-btn {
    display: flex;
    align-items: center;
    padding: 3px 10px;
    height: 2rem;
    border: 2px solid silver;
    border-radius: 10px;
    white-space: nowrap;
    cursor: pointer;

  &:not(:first-child) {
     margin-left: 5px;
   }
  }

  .bar-btn__icon {
    margin-right: 5px;
    height: 15px;
    width: 15px;
    background: silver;
  }

  .bar-btn__text {
    color: gray;
    font-weight: 500;
  }

  .fade-enter-active, .fade-leave-active {
    transition: all .4s cubic-bezier(2.0, 2.5, 2.8, 2.0);
  }

  .fade-enter-from, .fade-leave-to {
    transform: translateY(-20px);
    opacity: 0;
  }
</style>