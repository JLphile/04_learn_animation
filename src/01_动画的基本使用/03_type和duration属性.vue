<template>
  <div class="app">
    <div><button @click="isShow = !isShow">显示/隐藏</button></div>

    <transition
      name="why"
      type="transition"
      :duration="{ enter: 800, leave: 1000 }"
    >
      <h2 class="title" v-if="isShow">{{ message }}</h2>
    </transition>
  </div>
</template>

<script>
export default {
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
.why-enter-from,
.why-leave-to {
  opacity: 0;
}
.why-enter-active,
.why-leave-active {
  transition: opacity 1s ease;
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
    transform: scale(1.5);
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
