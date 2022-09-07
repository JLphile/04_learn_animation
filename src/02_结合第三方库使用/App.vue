<template>
  <div class="app">
    <div><button @click="isShow = !isShow">显示/隐藏</button></div>
    <!-- 实现 一 -->
    <!-- <transition name="why" mode="out-in" :appear="true">
      <h2 class="title" v-if="isShow">{{ message }}</h2>
    </transition> -->

    <!-- 实现 二 -->
    <transition
      enter-active-class="animate__animated animate__fadeInUp"
      leave-active-class="animate__animated animate__slideOutDown"
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
/* .title {
  display: inline-block;
}
.why-enter-active {
  animation: bounceInUp 1s ease-in;
}
.why-leave-active {
  animation: bounceInUp 1s ease-in reverse;
} */
animate__slideOutDown {
  animation-direction: reverse;
}
</style>
