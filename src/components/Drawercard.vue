<template>
  <div class="card">
    <ul>
      <li>Drawercard1</li>
      <li>Drawercard2</li>
      <li>Drawercard3</li>
      <li>Drawercard4</li>
      <li>Drawercard5</li>
      <li>Drawercard6</li>
    </ul>
  </div>
</template>

<script setup></script>

<style scoped>
.card {
  width: 100%;
  height: 100%;
  background-color: #f7f7f7;
  border-radius: 10px;
  overflow: hidden;
}
/* li横向排列 */
.card ul {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
}

.card ul li {
  width: 18%;
  height: 100px;
  margin-left: 10px;
  background-color: #fd8484;
  border-radius: 10px;
  float: left;
}
</style>
