<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>

    <div class="content-box">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
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
      list: [
        {
          title: "促销",
          children: [
            {
              title: "最忆是杭州",
            },
            {
              title: "杭州口袋屋蹦床",
            },
            {
              title: "西湖外事游船",
            },
          ],
        },
        {
          title: "门票",
        },
        {
          title: "促销",
        },
        {
          title: "促销",
        },
        {
          title: "促销",
        },
      ],
    };
  },
};
</script>

<style lang="stylus" scoped>
.content-box {
  height: 50rem;
}
</style>