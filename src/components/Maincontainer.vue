<template>
  <div class="blur" v-show="isblur"></div>
  <div class="main-container">
    <div class="logo-area">
      <div class="img-shadow"></div>
      <div class="inner">
        <img class="logo" src="/src/assets/vue.svg" />
      </div>
    </div>
    <Search />
  </div>
</template>

<script setup>
import Search from './Search.vue';
const props = defineProps({
  isblur: Boolean,
});
</script>

<style scoped>
.main-container {
  width: 300px;
  height: 300px;
  position: absolute;
  left: 50%;
  top: 30%;
  transform: translate(-50%, -50%);
}
/* Logo区域 */
.logo-area {
  align-items: center;
  justify-content: center;
  display: flex;
  animation: logoEnter 1.2s;
  animation-fill-mode: forwards;
  transition: all 0.8s;
  background-size: cover !important;
  background-position: center !important;
}

/* Logo内部 */
.inner {
  position: relative;
  cursor: pointer;
}

/* 实现遮盖层 */
.blur {
  position: absolute;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.5);
  backdrop-filter: blur(10px);
  z-index: 2;
}
</style>
