<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" alt />
      <div class="banner-info">
        <div class="banner-num">
          <span class="iconfont">&#xe612;</span>
          <span>{{galleryImgs.length}}</span>
        </div>
        <div class="banner-tt">{{sightName}}</div>
      </div>
    </div>
    <common-fade>
      <common-gallery
        :img-list="galleryImgs"
        v-show="isGalleryShow"
        @closeGallery="handleGalleryClose"
      ></common-gallery>
    </common-fade>
  </div>
</template>

<script>
import CommonGallery from "common/gallery/Gallery";
import CommonFade from "common/fade/Fade";
export default {
  name: "DetailBanner",
  props: {
    sightName: String,
    bannerImg: String,
    galleryImgs: Array,
  },
  components: {
    "common-gallery": CommonGallery,
    "common-fade": CommonFade,
  },
  data: function () {
    return {
      isGalleryShow: false,
    };
  },
  methods: {
    handleBannerClick: function () {
      this.isGalleryShow = true;
    },
    handleGalleryClose: function () {
      this.isGalleryShow = false;
    },
  },
};
</script>

<style lang="stylus" scoped>
.banner {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 55%;
  background-color: #eee;
}

.banner .banner-img {
  width: 100%;
}

.banner .banner-info {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  color: #fff;
  line-height: 0.6rem;
  padding: 0 0.2rem 0.2rem;
  background-image: linear-gradient(to bootom, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));
}

.banner .banner-info .banner-num {
  width: 1.2rem;
  height: 0.6rem;
  line-height: 0.6rem;
  background-color: rgba(0, 0, 0, 0.5);
  border-radius: 0.2rem;
  font-size: 0.24rem;
  text-align: center;
}

.banner .banner-info .banner-tt {
  width: 100%;
  height: 0.6rem;
  line-height: 0.6rem;
  font-size: 0.36rem;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.7);
}
</style>