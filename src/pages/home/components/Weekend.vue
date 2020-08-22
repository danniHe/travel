<template>
  <div class="recommend-wrap">
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <router-link
        tag="li"
        class="list-item"
        to="/detail"
        v-for="item in weekendList"
        :key="item.id"
      >
        <div class="item-img">
          <img :src="item.imgUrl" alt />
        </div>
        <div class="item-info">
          <div class="info-title">{{item.title}}</div>
          <div class="info-desc">{{item.desc}}</div>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeWeekend",
  props: {
    weekendList: Array,
  },
};
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
@import '~styles/mixins.styl';

div {
  box-sizing: border-box;
}

.recommend-title {
  width: 100%;
  height: 0.8rem;
  line-height: 0.8rem;
  font-size: 0.28rem;
  background-color: #FFF0F5;
  padding: 0 0.2rem;
}

.list-item .item-img {
  width: 100%;
  height: 0;
  padding-bottom: 37.1%;
}

.list-item .item-img img {
  width: 100%;
}

.list-item .item-info {
  padding: 0.14rem 0.2rem 0.2rem;
}

.list-item .item-info .info-title {
  width: 100%;
  height: 0.6rem;
  line-height: 0.48rem;
  font-size: 0.28rem;
  ellipsis();
}

.list-item .item-info .info-desc {
  width: 100%;
  padding-right: 1.4rem;
  height: 0.42rem;
  line-height: 0.42rem;
  font-size: 0.24rem;
  color: $lightTxtColor;
  ellipsis();
}
</style>