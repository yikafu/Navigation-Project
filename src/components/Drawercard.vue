<template>
  <div class="card">
    <div class="select_spans">
      <span v-for="(key, index) in Object.keys(datas)" :key="index">{{key}}</span>
    </div>

    <ul v-for="(key, index) in Object.keys(datas)" :key="index">
      <li v-for="(item , index) in datas[key]" :key="index">
        <a :href="item.url">
          <span>{{item.name}}</span>
          <p>{{item.url}}</p>
        </a>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import data from "../data/data.json";
const datas = ref(data);

onMounted(() => {
  handleClick();
});

// 设置点击事件
function handleClick() {
  const spans = document.querySelectorAll(".select_spans span");
  const pages = document.querySelectorAll(".card ul");
  spans.forEach((span, index) => {
    span.addEventListener("click", () => {
      spans.forEach((span) => span.classList.remove("active_span"));
      span.classList.add("active_span");
      pages.forEach((page) => page.classList.remove("active"));
      pages[index].classList.add("active");
    });
  });
}
</script>

<style scoped>
.card {
  width: 100%;
  height: 100%;
  background-color: #f7f7f7;
  border-radius: 10px;
  overflow: hidden;
}
/* li横向排列，卡片布局 */
.card ul {
  display: none;
}

.card ul li {
  height: 100px;
  margin-left: 10px;
  background-color: #fd8484;
  border-radius: 10px;
}

.card ul li a {
  width: 100%;
  height: 100%;
  display: block;
}

.select_spans {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 40px;
  border-bottom: 1px solid #000000;
  margin-bottom: 8px;
}

.select_spans span {
  font-size: 14px;
  cursor: pointer;
}

.select_spans span:hover {
  color: #fd8484;
}

.active_span {
  color: #1162f7;
}
.active {
  display: grid !important;
  grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
  grid-gap: 20px;
}
</style>
