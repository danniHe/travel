<template>
  <div>
    <detail-banner 
      :sightName="sightName" 
      :bannerImg="bannerImg"
      :galleryImgs="galleryImgs"
    ></detail-banner>
    <detail-header></detail-header>

    <div class="content-box">
      <detail-list :list="categoryList"></detail-list>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import DetailBanner from "./components/Banner";
import DetailHeader from "./components/Header";
import DetailList from "./components/List";

export default {
  name: "Detail",
  components: {
    "detail-banner": DetailBanner,
    "detail-header": DetailHeader,
    "detail-list": DetailList,
  },
  data: function () {
    return {
      sightName: '',
      bannerImg: '',
      galleryImgs: [],
      categoryList: []
    };
  },
  methods: {
    getDetailInfo: function () {
      // axios.get("/api/detail.json?id=" + this.$route.params.id).then();
      axios
        .get("/api/detail.json", {
          params: {
            id: this.$route.params.id,
          },
        })
        .then(this.getDetailInfoSuccess);
    },
    getDetailInfoSuccess: function (res) {
      if (res.data.ret && res.data.data) {
        var data = res.data.data;
        this.sightName = data.sightName;
        this.bannerImg = data.bannerImg;
        this.galleryImgs = data.galleryImgs;
        this.categoryList = data.categoryList;
      }
    },
  },
  mounted: function () {
    this.getDetailInfo();
  },
};
</script>

<style lang="stylus" scoped>
.content-box {
  height: 50rem;
}
</style>