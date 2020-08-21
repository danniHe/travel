<template>
  <div class="icons-wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, idx) in pages" :key="idx">
        <div class="icon-box" v-for="item in page" :key="item.id">
          <div class="icon-img-box">
            <img class="icon-img" :src="item.imgUrl" />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>

      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeIcons",
  props: {
    iconList: Array,
  },
  data: function () {
    return {
      swiperOption: {
        autoplay: false,
      },
    };
  },
  computed: {
    pages: function () {
      var pages = [];
      this.iconList.forEach(function (item, idx) {
        var page = Math.floor(idx / 8);
        if (!pages[page]) {
          pages[page] = [];
        }
        pages[page].push(item);
      });
      return pages;
    },
  },
};
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
@import '~styles/mixins.styl';

.icons-wrapper {
  width: 100%;
  height: 0;
  padding-bottom: 50%;
  overflow: hidden;
  margin: 0.2rem 0;
}

.icons-wrapper .icon-box {
  position: relative;
  float: left;
  width: 25%;
  padding-bottom: 25%;
}

.icons-wrapper .icon-box .icon-img-box {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0.44rem;
}

.icons-wrapper .icon-box .icon-img-box .icon-img {
  display: block;
  height: 100%;
  margin: 0 auto;
}

.icons-wrapper .icon-box .icon-desc {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 0.44rem;
  line-height: 0.44rem;
  text-align: center;
  color: $darkTxtColor;
  ellipsis();
}
</style>