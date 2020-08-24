<template>
  <div>
    <div class="banner" @click="handleBannerClick">
    <img
      class="banner-img"
      src="//img1.qunarzz.com/sight/p0/1709/28/288fbeccc335f774a3.img.jpg_600x330_7511d912.jpg"
      alt
    />
    <div class="banner-info">
      <div class="banner-num">
        <span class="iconfont">&#xe612;</span>11
      </div>
      <div class="banner-tt">印象西湖</div>
    </div>    
  </div>
  <common-gallery 
    :img-list="imgList" 
    v-show="isGalleryShow" 
    @closeGallery="handleGalleryClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: "DetailBanner",  
  components: {
    'common-gallery': CommonGallery
  },
  data: function(){
    return{
      isGalleryShow: false,
      imgList: ['//img1.qunarzz.com/sight/p0/1709/28/288fbeccc335f774a3.img.jpg_600x330_7511d912.jpg',
      'http://img1.qunarzz.com/sight/p0/1709/93/939774ae36224b64a3.img.jpg_350x240_53357927.jpg']
    }
  },
  methods: {
    handleBannerClick: function(){
      this.isGalleryShow = true;
    },
    handleGalleryClose: function(){
      this.isGalleryShow = false;
    }
  }
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
  background-image: linear-gradient(to bootom, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
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
  text-shadow: 0 1px 2px rgba(0, 0, 0, .7);
}
</style>