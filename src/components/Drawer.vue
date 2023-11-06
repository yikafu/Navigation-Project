<template>
  <div class="drawer">
    <div class="drawer-container">
      <h2>show drawer</h2>
    </div>
  </div>
</template>

<script setup>
import { defineProps, watch } from "vue";
const props = defineProps({
  isshow: Boolean,
});

// 当isshow变化时，为drawer-container添加show或hidden类
watch(
  () => props.isshow,
  (val) => {
    const drawerContainer = document.querySelector(".drawer-container");
    if (val) {
      drawerContainer.classList.add("show");
      drawerContainer.classList.remove("hidden");
    } else {
      drawerContainer.classList.add("hidden");
      drawerContainer.classList.remove("show");
    }
  }
);
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
  background-color: #f7f7f7;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  transform: translate3d(-50%, 0, 0);
  opacity: 0;
  animation-fill-mode: forwards;
}

.show {
  opacity: 1;
  animation: InScreen 1s;
}

.hidden {
  opacity: 0;
  animation: OutScreen 1s;
}

@keyframes OutScreen {
  from {
    opacity: 1;
    transform: translate3d(-50%, 0, 0);
  }
  to {
    transform: translate3d(-50%, 100%, 0);
  }
}

@keyframes InScreen {
  from {
    opacity: 0;
    transform: translate3d(-50%, 100%, 0);
  }
  to {
    transform: translate3d(-50%, 0, 0);
  }
}
</style>
