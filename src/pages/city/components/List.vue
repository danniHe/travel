<template>
  <div class="listWrapper" ref="listWrapper">
    <div>
      <div class="hot-cities">
        <div class="hot-cities-tt">热门城市</div>
        <ul class="clearfix">
          <li
            v-for="item in computedHotCities"
            :key="item.id"
            :class="item.borderType"
          >{{item.name}}</li>
        </ul>
      </div>
      <div class="alhpabet-menu">
        <div class="alhpabet-menu-tt">字母排序</div>
        <ul class="clearfix">
          <li v-for="item in cities" :key="item.initial" @click="handleAlhpabetClick">{{item.initial}}</li>
        </ul>
      </div>
      <div class="alhpabet-list" v-for="item in cities" :key="item.initial" :ref="item.initial">
        <div class="alhpabet-list-tt">{{item.initial}}</div>
        <ul class="clearfix">
          <li v-for="(innerItem, key) in item.list" :key="key">{{innerItem.name}}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from "better-scroll";

export default {
  name: "CityList",
  props: {
    hotCities: Array,
    cities: Array,
  },
  data: function(){
    return {
      letter: ''
    }
  },
  methods: {
    handleAlhpabetClick: function(e){
      this.letter = e.target.innerText;      
    }
  },
  computed: {
    computedHotCities: function () {
      var res = [],
        len = this.hotCities.length,
        item;
      // res = [{borderType = '边框', name = '城市名'}]
      for (var i = 0; i < len; i++) {
        var resObj = {};
        item = this.hotCities[i];
        resObj.name = item.name;
        res.push(resObj);

        if (item.order === 1) {
          resObj.borderType = "";
        } else if (item.order === 2 || item.order === 3) {
          resObj.borderType = "border-left";
        } else if (item.order % 3 === 1) {
          resObj.borderType = "border-top";
        } else {
          resObj.borderType = "border-topleft";
        }
      }
      return res;
    }
  },
  mounted: function () {
    this.scroll = new BScroll(".listWrapper");
    // this.scroll = new BScroll(this.$refs.listWrapper)    
  },
  watch: {
    letter: function(){
      var el = this.$refs[this.letter][0];
      this.scroll.scrollToElement(el);
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';

div {
  box-sizing: border-box;
}

.clearfix::after {
  display: table;
  content: '';
  clear: both;
}

.listWrapper {
  position: absolute;
  top: 0.88rem;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
}

.hot-cities {
  width: 100%;
  height: 4.32rem;
}

.hot-cities .hot-cities-tt, .alhpabet-menu .alhpabet-menu-tt, .alhpabet-list .alhpabet-list-tt {
  width: 100%;
  height: 0.72rem;
  line-height: 0.72rem;
  padding: 0 0.2rem;
  font-size: 0.26rem;
  color: $darkTxtColor;
  background-color: #f5f5f5;
}

.hot-cities ul li {
  float: left;
  width: 33.33%;
  height: 0.9rem;
  line-height: 0.9rem;
  text-align: center;
}

.alhpabet-menu ul {
  height: 4.2rem;
  margin: 0.3rem 0;
}

.alhpabet-menu ul li {
  float: left;
  width: 16.67%;
  height: 0.9rem;
  line-height: 0.9rem;
  text-align: center;
}

.alhpabet-list ul li {
  float: left;
  width: 25%;
  height: 0.9rem;
  line-height: 0.9rem;
  text-align: center;
}
</style>