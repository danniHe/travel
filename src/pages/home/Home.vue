<template>
  <div>
    <home-header></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recommend :recommendList="recommendList"></home-recommend>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from "./components/Header.vue";
import HomeSwiper from "./components/Swiper.vue";
import HomeIcons from "./components/Icons.vue";
import HomeRecommend from "./components/Recommend.vue";
import HomeWeekend from "./components/Weekend.vue";
import axios from "axios";
import { mapState } from "vuex";

export default {
  name: "Home",
  components: {
    HomeHeader: HomeHeader,
    HomeSwiper: HomeSwiper,
    HomeIcons: HomeIcons,
    HomeRecommend: HomeRecommend,
    HomeWeekend: HomeWeekend,
  },
  computed: {
    ...mapState({
      curCity: "city",
    }),
  },
  data: function () {
    return {
      lastCity: "",
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: [],
    };
  },
  methods: {
    getHomeInfo: function () {
      axios
        .get("/api/index.json?city=" + this.curCity)
        .then(this.getHomeInfoSuccess);
    },
    getHomeInfoSuccess: function (res) {
      if (res.data.ret && res.data.data) {
        var data = res.data.data;
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
      }
    },
  },
  mounted: function () {
    this.lastCity = this.curCity;
    this.getHomeInfo();
  },
  // 切换了城市，发送请求
  activated: function () {
    if (this.lastCity !== this.curCity) {
      this.lastCity = this.curCity;
      this.getHomeInfo();
    }
  },
};
</script>

<style>
</style>