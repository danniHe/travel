<template>
  <div class="recommend-wrap">
    <div class="recommend-title">
      <span class="iconfont icon-heart">&#xe604;</span> 猜你喜欢
    </div>
    <ul>
      <router-link
        tag="li"
        class="list-item"
        :to="'/detail/' + item.id"
        v-for="item in recommendList"
        :key="item.id"
      >
        <div class="item-img">
          <img :src="item.imgUrl" alt />
        </div>
        <div class="item-img-tag">{{item.tag}}</div>
        <div class="item-info">
          <div class="inner-box">
            <div class="info-title">{{item.title}}</div>
            <div class="info-comment">
              <span class="iconfont icon-star">&#xe6b9;</span>
              <span class="iconfont icon-star">&#xe6b9;</span>
              <span class="iconfont icon-star">&#xe6b9;</span>
              <span class="iconfont icon-star">&#xe6b9;</span>
              <span class="iconfont icon-star">&#xe6b9;</span>
              <span class="comment-num">{{item.commentNum}}条评论</span>
            </div>
            <div class="info-price">
              <span class="price">
                ￥
                <em>{{item.price}}</em>
              </span>起
              <span class="district">{{item.district}}</span>
            </div>
          </div>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  props: {
    recommendList: Array,
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
  font-size: 0.3rem;
  background-color: #FFF0F5;
  padding: 0 0.2rem;
}

.recommend-title .icon-heart {
  color: #CD2626;
}

.list-item {
  display: flex;
  position: relative;
  width: 100%;
  height: 2.4rem;
}

.list-item .item-img {
  width: 2.4rem;
  height: 2.4rem;
  padding: 0.2rem;
}

.list-item .item-img img {
  width: 100%;
  height: 100%;
}

.list-item .item-img-tag {
  position: absolute;
  top: 0.2rem;
  left: 0.2rem;
  width: 1.02rem;
  height: 0.38rem;
  line-height: 0.38rem;
  background-image: url('https://img1.qunarzz.com/piao/fusion/1802/52/b9080e45b69b4f02.png');
  background-size: 100% 100%;
  font-size: 0.2rem;
  color: #fff;
  text-indent: 0.04rem;
}

.list-item .item-info {
  flex: 1;
  padding: 0.4rem 0.1rem;
  min-width: 0;
}

.list-item .item-info .inner-box {
  width: 100%;
  height: 100%;
}

.list-item .item-info .inner-box .info-title {
  width: 100%;
  height: 0.6rem;
  line-height: 0.6rem;
  font-size: 0.32rem;
  ellipsis();
}

.list-item .item-info .inner-box .info-comment {
  width: 100%;
  height: 0.4rem;
  line-height: 0.4rem;
  font-size: 0.24rem;
}

.list-item .item-info .inner-box .info-comment .icon-star {
  font-size: 0.2rem;
  color: #ffb436;
}

.list-item .item-info .inner-box .info-comment .comment-num {
  color: $lightTxtColor;
}

.list-item .item-info .inner-box .info-price {
  position: relative;
  width: 100%;
  height: 0.6rem;
  line-height: 0.6rem;
  color: $lightTxtColor;
}

.list-item .item-info .inner-box .info-price .price {
  color: #ff8300;
}

.list-item .item-info .inner-box .info-price .price em {
  font-size: 0.4rem;
}

.list-item .item-info .inner-box .info-price .district {
  position: absolute;
  bottom: 0;
  right: 0.24rem;
}
</style>