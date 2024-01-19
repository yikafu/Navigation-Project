<template>
  <div id="search">
    <form
      action="https://www.bing.com/search"
      target="_blank"
      @click="submitForm"
    >
      <input
        type="text"
        name="q"
        placeholder="输入搜索内容"
        v-model="searchText"
      />
      <button type="submit">搜索</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

const searchText = ref("");

function submitForm() {
  searchText.value = "";
}
</script>

<style>
#search {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
}

form {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #fff;
  border-radius: 31px;
}

input[type="text"] {
  width: 550px;
  height: 40px;
  color: #000000;
  padding: 5px 18px;
  margin-right: 8px;
  border-radius: 31px;
}

button[type="submit"] {
  width: 55px;
  height: 40px;
  font-size: 14px;
  color: #000000;
  border-left: 1px #ccc solid;
  cursor: pointer;
}
button[type="submit"]:hover {
  color: #06554f;
}
</style>
