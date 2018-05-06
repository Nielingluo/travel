<template>
    <div class="header">
        城市选择
      <router-link to="/">
        <div class="iconfont header-icon">&#xe624;</div>
      </router-link>
    </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .header
    position relative
    overflow hidden
    line-height $headerHeight
    height $headerHeight
    text-align center
    color #ffffff
    background $bgColor
    .header-icon
      position absolute
      left: 0
      top: 0
      width .64rem
      text-align center
      font-size .4rem
      color #fff
</style>
