<template>
  <div class="app">
    <div><button @click="isShow = !isShow">显示/隐藏</button></div>

    <transition name="why" mode="out-in" :appear="true">
      <component :is="isShow ? 'Home' : 'About'"></component>
    </transition>
  </div>
</template>

<script>
import Home from './pages/Home.vue';
import About from './pages/About.vue';
export default {
  components: {
    Home,
    About,
  },
  data() {
    return {
      message: 'Hello World',
      isShow: true,
    };
  },
};
</script>

<style scoped>
.title {
  display: inline-block;
}
.why-enter-active {
  animation: bounce 1s ease;
}
.why-leave-active {
  animation: bounce 1s ease reverse;
}
@keyframes bounce {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}
.app {
  width: 200px;
  margin: 0 auto;
}
</style>
