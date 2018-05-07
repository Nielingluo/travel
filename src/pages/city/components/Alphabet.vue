<template>
    <div class="list">
      <ul>
        <li class="item" v-for="item of letters" :key="item" :ref="item" @click="handleLetterClick" @touchstart="handleTouchStart" @touchmove="handleTouchMove" @touchend="handleTouchEnd">{{item}}</li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  data () {
    return {
      touchStaus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop // A字母距离顶部的高度
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStaus = true
    },
    handleTouchMove (e) {
      if (this.touchStaus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79 // 手指距离最顶部的距离 - 79（蓝色区域高度）
          const index = Math.floor((touchY - this.startY) / 20) // 除以字母高度20   最终获取当前手指滑动的位置对应的字母下标
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStaus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .list
    display flex
    flex-direction column
    justify-content center
    position absolute
    top:1.58rem
    right:0
    bottom 0
    width .4rem
    .item
      height .4rem
      text-align center
      color $bgColor
</style>
