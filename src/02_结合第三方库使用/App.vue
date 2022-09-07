<template>
  <div class="app">
    <div><button @click="isShow = !isShow">显示/隐藏</button></div>

    <transition name="why" mode="out-in" :appear="true">
      <h2>{{ message }}</h2>
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

<style scoped></style>
