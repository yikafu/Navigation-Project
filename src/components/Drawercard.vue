<template>
  <div class="select-spans">
    <span v-for="(key, index) in Object.keys(datas)" :key="index">{{
      key
    }}</span>
  </div>
  <div class="card">
    <div
      class="card-container"
      v-for="(key, index) in Object.keys(datas)"
      :key="index"
    >
      <a
        :href="item.url"
        target="_blank"
        v-for="(item, index) in datas[key]"
        :key="index"
      >
        <div class="icon">
          {{ item.name[0] }}
        </div>
        <div class="info">
          <div class="title">{{ item.name }}</div>
          <div class="description">{{ item.description }}</div>
        </div>
      </a>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import data from "@/data/data.js";
const datas = ref(data);

onMounted(() => {
  handleClick();
});

// 设置点击事件
function handleClick() {
  const spans = document.querySelectorAll(".select-spans span");
  const pages = document.querySelectorAll(".card-container");

  spans[0].classList.add("active-span");
  pages[0].classList.add("active");

  spans.forEach((span, index) => {
    span.addEventListener("click", () => {
      spans.forEach((span) => span.classList.remove("active-span"));
      span.classList.add("active-span");
      pages.forEach((page) => page.classList.remove("active"));
      pages[index].classList.add("active");
    });
  });
}
</script>

<style scoped>
/* card区域 */
.card {
  width: 100%;
  height: 100%;
  background-color: #f7f7f7;
  border-radius: 10px;
  overflow-y: auto;
  padding: 10px;
  box-sizing: border-box;
}
.card-container {
  display: none;
}
.card-container a {
  height: 100px;
  background-color: #ececec;
  border-radius: 10px;
  display: flex;
}

/* 选择区域 */
.select-spans {
  height: 40px;
  border-bottom: 1px solid #000000;
  margin-bottom: 8px;
  display: flex;
  align-items: center;
}
.select-spans span {
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  margin: 0 1rem;
}
.active-span {
  color: #1162f7;
}
.active {
  display: grid !important;
  grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
  grid-gap: 20px;
}

/* 图标区  信息区*/
.icon {
  width: 100px;
  height: 100px;
  font-size: 2.2rem;
  color: #f7f7f7;
  background-color: #5a5a5a;
  border-radius: 100%;
  transform: scale(0.8);
  text-align: center;
  line-height: 100px;
}
.info {
  width: calc(100% - 100px);
  font-size: 12px;
  word-wrap: break-word;
  word-break: break-all;
  padding: 10px;
}
.title {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 5px;
}
.description {
  font-size: 12px;
  color: #5a5a5a;
}
</style>
