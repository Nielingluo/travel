<template>
    <div>
      <div class="banner" @click="handleBannerClick">
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1710/7f/7f06f56b02987c66a3.img.jpg_600x330_029cf445.jpg" alt="">
        <div class="banner-info">
          <div class="banner-title">库木塔格沙漠公园</div>
          <div class="banner-number"><span class="iconfont banner-icon">&#xe604;</span>8</div>
        </div>
      </div>
      <fade-animation>
        <Common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></Common-gallary>
      </fade-animation>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1710/7f/7f06f56b02987c66a3.img.jpg_r_800x800_eb8da27f.jpg', 'http://img1.qunarzz.com/sight/p0/1710/7f/7f06f56b02987c66a3.img.jpg_r_800x800_eb8da27f.jpg'
      ]
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary,
    FadeAnimation
  }
}
</script>

<style lang="stylus" scoped>
    .banner
      position relative
      overflow hidden
      height: 0
      padding-bottom 55%
      .banner-img
        width 100%
      .banner-info
        display: flex
        position absolute
        left:0
        right 0
        bottom 0
        line-height .6rem
        color #fff
        background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.7))
        .banner-title
          flex 1
          font-size .32rem
          padding 0 .2rem
        .banner-number
          height:.32rem
          line-height .32rem
          margin-top .14rem
          padding 0 .4rem
          border-radius .2rem
          background rgba(0,0,0,.8)
          font-size .24rem
          .banner-icon
            font-size .24rem
            margin-right .1rem
</style>
