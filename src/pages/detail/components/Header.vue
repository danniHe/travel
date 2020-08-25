<template>
  <div>
    <router-link tag="div" to="/" class="header-back" v-show="showHeaderBack">
      <span class="iconfont icon-back">&#xe600;</span>
    </router-link>
    <div class="header" :style="opacityStyle" v-show="!showHeaderBack">
      <router-link to="/" class="header-left iconfont">&#xe600;</router-link>印象西湖
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailHeader",
  data: function () {
    return {
      showHeaderBack: true,
      opacityStyle: {
        opacity: 0
      }
    };
  },
  methods: {
    handleScroll: function () {      
      var top = document.documentElement.scrollTop;
      if (top > 30) {
        var opacity = top / 100;
        opacity = opacity > 1 ? 1 : opacity;        
        this.opacityStyle.opacity = opacity;
        this.showHeaderBack = false;
      }else{
        this.showHeaderBack = true;
      }
    },
  },
  activated: function () {
    window.addEventListener("scroll", this.handleScroll);
  },
  deactivated: function(){
    window.removeEventListener("scroll", this.handleScroll);
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';

.header-back {
  position: absolute;
  top: 0.2rem;
  left: 0.2rem;
  width: 0.72rem;
  height: 0.72rem;
  line-height: 0.72rem;
  text-align: center;
  border-radius: 0.4rem;
  background-color: rgba(0, 0, 0, 0.5);
}

.header-back .icon-back {
  font-size: 0.36rem;
  color: #fff;
}

.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 0.88rem;
  line-height: 0.88rem;  
  color: #fff;
  text-align: center;
  font-size: 0.36rem;
  background-color: $bgColor;
  z-index: 3;
}

.header .header-left {
  position: absolute;
  top: 0;
  left: 0;
  display: inline-block;
  width: 0.8rem;
  height: 0.88rem;
  text-align: center;
  font-size: 0.36rem;
  color: #fff;
}
</style>