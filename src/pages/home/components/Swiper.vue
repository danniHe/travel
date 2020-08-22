<template>
  <div class="sw-wrapper">
    <swiper :options="swiperOption" v-if="isSwiperShow">
      <swiper-slide v-for="item in swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>

      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  props: {
    swiperList: Array,
  },
  data: function () {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: true,
      },
    };
  },
  computed: {
    isSwiperShow: function () {
      return this.swiperList.length;
    },
  },
};
</script>

<style lang="stylus" scoped>
.sw-wrapper >>> .swiper-pagination-bullet-active {
  background-color: #fff;
}

.sw-wrapper {
  overflow: hidden;
  width: 100%;
  height: 0;
  // 100/375 = 0.26666`
  padding-bottom: 26.67%;
  background: #eee;
}

// 图片大小：375*100
.sw-wrapper .swiper-img {
  width: 100%;
  height: 100%;
}
</style>