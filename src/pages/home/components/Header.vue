<template>
  <div class="header">
    <div class="header-left">header</div>
    <div class="header-middle"></div>
    <div class="header-right"></div>
  </div>
</template>

<script>
export default {
  name: "HomeHeader",
};
</script>

<style lang="stylus" scoped>
.header {
  display: flex;
  width: 100%;
  height: 0.88rem;
  background-color: red;
}

.header .header-left {
  width: 0.8rem;
  height: 100%;
  background-color: orange;
}

.header .header-middle {
  flex: 1;
  background-color: blue;
}

.header .header-right {
  width: 0.8rem;
  height: 100%;
  background-color: green;
}
</style>