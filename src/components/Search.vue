<template>
  <div id="search">
    <div class="form">
      <input class="search-input" placeholder="输入搜索内容" v-model="searchText" />
      <button class="search-button" @click="handleClick">搜索</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const searchText = ref("");
const handleClick = () => {
  if (!searchText.value) {
    alert("请输入搜索内容");
    return;
  }
  window.open(`https://cn.bing.com/search?q=${searchText.value}`);
};
</script>

<style scoped>
#search {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
}

.form {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #fff;
  border-radius: 31px;
}

.search-input {
  width: 550px;
  height: 40px;
  color: #000000;
  padding: 5px 18px;
  margin-right: 8px;
  border-radius: 31px;
}

.search-button {
  width: 55px;
  height: 40px;
  font-size: 14px;
  color: #000000;
  border-left: 1px #ccc solid;
  cursor: pointer;
}
.search-button:hover {
  color: #06554f;
}
</style>
