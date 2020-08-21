<template>
  <div class="recommend-wrap">
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <router-link
        tag="li"
        class="list-item"
        to="/detail"
        v-for="item in recommendList"
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
  data: function () {
    return {
      recommendList: [
        {
          id: "001",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1811/52/b6776b49d27025.jpg_r_640x214_35ae205c.jpg",
          title: "美丽普陀山",
          desc:
            "人间仙境杭州，佛教圣地普陀山等你来玩！在这里静心接收佛家的洗礼，用心感受佛文化",
        },
        {
          id: "002",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg",
          title: "杭州必打卡",
          desc: "杭州，前世今生与你有一场美丽约会",
        },
        {
          id: "003",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/9f/7d45cc38259e0.jpg_r_640x214_156f4299.jpg",
          title: "承载杭城的历史之地",
          desc: "饱经沧桑的地方诉述着这座城的段段衷肠",
        },
      ],
    };
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
  padding: 0.14rem 0.2rem .2rem; 
}

.list-item .item-info .info-title {
  width: 100%;
  height: 0.6rem;
  line-height: 0.48rem;
  font-size: 0.28rem;
  ellipsis();
}

.list-item .item-info .info-desc{
  width: 100%;
  padding-right: 1.4rem;
  height: .42rem;
  line-height : .42rem;
  font-size: .24rem;
  color: $lightTxtColor;
  ellipsis();
}
</style>