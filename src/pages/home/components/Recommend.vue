<template>
  <div>
    <div class="title">热销</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img :src="item.imgUrl" alt="" class="item-img">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>

</template>

<script>
export default {
  name: 'HomeRecommend',
  data: function () {
    return {
      recommendList: [
        {
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1803/1a/1aac2b1dd96b36ba3.water.jpg_200x200_8148509f.jpg',
          title: '上海欢乐谷',
          desc: '秒杀上海欢乐谷五一夜场特惠票'
        },
        {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          desc: '秒杀上海欢乐谷五一夜场特惠票'
        },
        {
          id: '003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/17/170481fb9caf500790.water.jpg_200x200_a32b9a92.jpg',
          title: '上海野生动物园',
          desc: '秒杀上海欢乐谷五一夜场特惠票'
        }

      ]
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
