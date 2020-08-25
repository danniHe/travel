<template>
  <div>
    <div class="list-item" v-for="(item, index) in list" :key="index">
      <div class="list-item-tt border-bottom">
        {{item.title}}
      </div>
      <!-- 递归组件 -->
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailList",
  props: {
    list: Array,
  },
};
</script>

<style lang="stylus" scoped>
.list-item-tt {
  width: 100%;
  height: 0.8rem;
  line-height: 0.8rem;
  font-size: 0.32rem;
  padding: 0 0.2rem;
}

.list-item .item-children{
  padding: 0 .2rem;
}
</style>