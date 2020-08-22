<template>
  <div class="list">
    <div>
      <div class="hot-cities">
        <div class="hot-cities-tt">热门城市</div>
        <ul class="clearfix">
          <li class="border-top">北京</li>
          <li class="border-topleft">北京</li>
          <li class="border-topleft">北京</li>
          <li class="border-top">北京</li>
          <li class="border-topleft">北京</li>
          <li class="border-topleft">北京</li>
          <li class="border-top">北京</li>
          <li class="border-topleft">北京</li>
          <li class="border-topleft">北京</li>
          <li class="border-top">北京</li>
          <li class="border-topleft">北京</li>
          <li class="border-topleft">北京</li>
        </ul>
      </div>
      <div class="alhpabet-menu">
        <div class="alhpabet-menu-tt">字母排序</div>
        <ul class="clearfix">
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
          <li>A</li>
        </ul>
      </div>
      <div class="alhpabet-list">
        <div class="alhpabet-list-tt">A</div>
        <ul class="clearfix">
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
          <li>阿拉尔</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CityList",
};
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'

div{
  box-sizing: border-box;
}

.clearfix::after{
  display: table;
  content: '';
  clear: both;
}

.list{
  position: absolute;
  top: .88rem;
  left: 0;
  right: 0;
  bottom: 0;
}

.hot-cities{
  width: 100%;
  height: 4.32rem;  
}

.hot-cities .hot-cities-tt,
.alhpabet-menu .alhpabet-menu-tt,
.alhpabet-list .alhpabet-list-tt{
  width: 100%;
  height: .72rem;
  line-height : .72rem;
  padding: 0 .2rem;
  font-size: .26rem;
  color: $darkTxtColor;
  background-color: #f5f5f5;
}

.hot-cities ul li {
  float: left;
  width: 33.33%;
  height: .9rem;
  line-height: .9rem;
  text-align: center;   
}

.alhpabet-menu ul{
  height: 4.2rem;
  margin: .3rem 0;
}

.alhpabet-menu ul li{
  float: left;
  width: 16.67%;
  height: .9rem;
  line-height : .9rem;
  text-align: center;
}

.alhpabet-list ul li {
  float: left;
  width: 25%;
  height: .9rem;
  line-height: .9rem;
  text-align: center;
}
</style>