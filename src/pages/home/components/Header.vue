<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe600;</span>
    </div>
    <div class="header-middle">
      <span class="iconfont search-icon">&#xe614;</span>
      <div class="kw">输入城市、景点、游玩主题</div>
      <input class="header-input" type="text" />
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <!-- {{this.$store.state.city}} -->
        <span class="iconfont">&#xe616;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  name: "HomeHeader",
  // props: {
  //   city: String
  // }
  // 辅助函数 mapState 将 this.city 隐射成 this.$store.state
  computed: {
    ...mapState({
      city: "city",
    })
  },
};
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';

.header {
  display: flex;
  width: 100%;
  height: 0.88rem;
  color: #fff;
  background-color: $bgColor;
}

.header .header-left {
  width: 0.8rem;
  height: 100%;
  text-align: center;
  line-height: 0.88rem;
}

.header .header-middle {
  position: relative;
  flex: 1;
  margin: 0.14rem 0;
}

.header .header-middle .search-icon {
  position: absolute;
  top: 0.13rem;
  left: 0.2rem;
  color: #e4e7ea;
}

.header .header-middle .kw {
  position: absolute;
  top: 0.16rem;
  left: 0.6rem;
  color: #e4e7ea;
}

.header .header-middle .header-input {
  width: 100%;
  height: 100%;
  border-radius: 0.06rem;
}

.header .header-right {
  min-width: 1.12rem;
  padding: 0 0.1rem;
  height: 100%;
  text-align: center;
  line-height: 0.88rem;
  color: #fff;
}
</style>