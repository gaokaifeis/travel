<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/201301/07/d40895cabac2af8a93835fbb.jpg_600x330_32b2aec7.jpg" />
      <div class="banner-info">
        <div class="banner-title">莫干山(AAAA景区)</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe7b0;</span>39</div>
      </div>
    </div>
    <common-gallary @close="handleGallaryClose" :imgs="imgs" v-show="showGallary"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'Banner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showGallary: false,
      imgs: [
        'http://img1.qunarzz.com/sight/p0/201308/28/fc9d40de765f5309c8d65eac.jpg_r_800x800_9fcfe571.jpg',
        'http://img1.qunarzz.com/sight/p0/201301/07/cc547f0d7e5e4aa793835fbb.jpg_r_800x800_22678c86.jpg'
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
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        margin-top: .14rem
        padding: 0 .4rem
        line-height: .32rem
        height: .32rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
