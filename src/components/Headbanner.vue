<template>
  <div class="banner">
    <h2>My Banner</h2>
    <ul class="banner-part">
      <li>Home</li>
      <li>Product</li>
      <li>Feature</li>
      <li>About</li>
    </ul>
    <ul class="banner-menu">
      <li>
        <a href="#">
          <!-- <img src="../assets/search.svg" alt="" /> -->
        </a>
      </li>
      <li>
        <a href="#">
          <!-- <img src="../assets//user.svg" alt="" /> -->
        </a>
      </li>
      <li>
        <a href="#">
          <!-- <img src="../assets/daytime-mode.svg" alt="" /> -->
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Headbanner",
  setup() {
    return {};
  },
};
</script>

<style scoped>
.banner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 64px;
  background: #aed0ee;
}
h2 {
  margin-left: 110px;
}

ul {
  display: flex;
  margin-left: 0.625rem;
  padding: 0;
}
li {
  margin: 0 20px;
  padding: 0 10px;
  min-width: 30px;
  text-align: center;
  background: linear-gradient(135deg, #f1ca74, #a64db6);
  background-size: 0 2px;
  background-repeat: no-repeat;
  background-position: bottom center;
  transition: 1s all;
}
li:hover {
  cursor: pointer;
  color: #a64db6;
  background-size: 100% 2px;
}

ul.banner-menu {
  margin-right: 110px;
}
ul.banner-menu li {
  margin: 0 10px;
}

@media screen and (max-width: 768px) {
  .banner-menu {
    justify-content: flex-end;
    width: 100%;
  }
  ul.user_region {
    margin-left: 0;
    margin-top: 0.625rem;
    margin-bottom: 0.625rem;
    overflow-x: auto;
    white-space: nowrap;
  }
  li {
    margin-right: 1.25rem;
    min-width: 30px;
    text-align: center;
    font-size: 0.8125rem;
  }
}
</style>
