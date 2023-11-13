<template>
  <div class="blur" v-show="isblur"></div>
  <div class="main-container">
    <div class="logo-area">
      <div class="img-shadow"></div>
      <div class="inner">
        <img class="logo" src="/src/assets/vue.svg" />
        <div class="hello-area">
          <div>Wellcome to this site</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  isblur: Boolean,
});
</script>

<style scoped>
.main-container {
  text-align: center;
  border-radius: 20px;
  width: 300px;
  height: 300px;
  position: absolute;
  left: 50%;
  top: 50%;
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

.hello-area {
  color: #000;
  width: 18.75rem;
  text-align: center;
  position: absolute;
  left: 50%;
  top: 200px;
  transform: translate(-50%, -50%);
  font-size: 1.5rem;
  opacity: 1;
  transition: all 1s;
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
