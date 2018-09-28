<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
      </div>
      <div class="banner-number">
        <span class="iconfont banner-icon" id="arrow-down">&#xe605;</span>
        {{this.bannerImgs.length}}
      </div>
    </div>
    <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose">
    </common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_r_800x800_6edd8174.jpg',
        'http://img1.qunarzz.com/sight/p55/201211/04/fbcab3e5d6479ce893835fbb.jpg_r_800x800_6360f514.jpg']
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
  components: { CommonGallary }
}
</script>
<style lang="stylus" scoped>
.banner
  position relative
  overflow hidden
  height 0
  padding-bottom 55%
  .banner-img
    width 100%
  .banner-info
    position absolute
    left 0.2rem
    right 0.2rem
    bottom 0.36rem
    min-height 0.4rem
    color #fff
  .banner-title
    line-height 0.4rem
    font-size 0.36rem
    text-shadow 0 1px 2px rgba(0, 0, 0, 0.7)
  .banner-number
    position absolute
    left 0.2rem
    bottom 0.86rem
    color #fff
    width 1.2rem
    height 0.4rem
    background rgba(0, 0, 0, 0.5)
    border-radius 0.2rem
    font-size 0.24rem
    line-height 0.4rem
    text-align center
    .banner-icon
      font-size 0.25rem
</style>
