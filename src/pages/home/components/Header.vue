<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont" id="back-icon">&#xe66b;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题</div>
    <div class="header-right">城市
      <span class="iconfont" id="arrow-down">&#xe73a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  line-height 0.86rem
  display flex
  background-color $bgColor
  color #fff
  .header-left
    width 0.64rem
    float left
    #back-icon
      text-align center
      font-size 0.4rem
  .header-input
    flex 1
    background-color #fff
    border-radius 0.1rem
    margin-top 0.12rem
    margin-left 0.2rem
    padding-left 0.2rem
    line-height 0.64rem
    height 0.64rem
    color #ccc
  .header-right
    width 1.24rem
    float right
    text-align center
    #arrow-down
      font-size 0.24rem
</style>
