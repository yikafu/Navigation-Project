<template>
  <transition name="fade">
    <div class="drawer" v-show="isshow">
      <div class="drawer-container">
        <Drawercard />
      </div>
    </div>
  </transition>
</template>

<script setup>
import Drawercard from './Drawercard.vue';
const props = defineProps({
  isshow: Boolean,
});
</script>

<style scoped>
.drawer {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 99;
}
.drawer-container {
  position: absolute;
  width: calc(100vw - 3rem);
  max-width: 2000px;
  height: 500px;
  padding: 10px;
  bottom: 30px;
  left: 50%;
  border-radius: 10px;
  background-color: #f7f7f7;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  transform: translateX(-50%);
}

.fade-enter-active,
.fade-leave-active {
  transition: all .8s ease;
}
.fade-enter-from,
.fade-leave-to {
  transform: translateY(100%);
}
.fade-enter-to,
.fade-leave-from{
  transform: translateY(0%);
}
</style>
