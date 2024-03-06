<template>
  <div class="down">
    <span>Whell Down</span>
    <img src="@/assets/down.svg" alt="" />
  </div>
</template>

<script></script>

<style scoped>
.down {
  position: fixed;
  bottom: 6%;
  left: 0;
  right: 0;
  text-align: center;
  color: #e7dfdf;
  font-size: 20px;
  font-weight: bold;
  padding: 10px;
  margin: auto;
  width: 150px;
}
.down img {
  margin-top: 10px;
  animation: down 1.5s infinite;
}

@keyframes down {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(10px);
  }
  100% {
    transform: translateY(0);
  }
}
</style>
