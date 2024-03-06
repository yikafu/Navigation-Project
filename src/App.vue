<template>
  <Maincontainer :isblur="isshow" />
  <Down />
  <Drawer :isshow="isshow" />
</template>

<script setup>
import { ref, onMounted } from "vue";

import Maincontainer from "./components/Maincontainer.vue";
import Down from "./components/Down.vue";
import Drawer from "./components/Drawer.vue";

const isshow = ref(false);

function changeShow() {
  window.addEventListener("wheel", handleWheelEvent);
}

function handleWheelEvent(e) {
  isshow.value = e.deltaY > 100;
}

onMounted(() => {
  changeShow();
});
</script>

<style>
body {
  overflow: hidden;
  background-image: url(@/assets/bg.jpeg);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  background-attachment: fixed;
}
</style>
