<template>
  <div>
    <div class="title">热销</div>
    <ul>
      <router-link class="item border-bottom" v-for="item of list" :key="item.id" :to="'/detail/'+ item.id" tag="li">
        <img :src="item.imgUrl" alt="" class="item-img">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>

</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  },
  data: function () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .title
    margin-top .2rem
    line-height .8rem
    background #eee
    text-indent .2rem
  .item
    display: flex
    overflow hidden
    height 1.9rem
    .item-img
      width 2rem
      height:2rem
      padding 0.1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
      .item-button
        line-height .44rem
        margin-top .16rem
        background #ff9300
        padding 0 .2rem
        border-radius .06rem
        color #fff
</style>
