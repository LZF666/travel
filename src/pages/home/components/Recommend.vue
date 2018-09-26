<template>
  <div>
    <div class="cut-off"></div>
    <ul>
      <div class="title">
        <img class="title-img" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt=""> 猜你喜欢
      </div>
        <router-link :to="'./detail/'+item.id" tag="li" class="item border-bottom" v-for="item of list" :key="item.id">

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
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.cut-off
  line-height 0.2rem
  height 0.2rem
  background #eee
.title
  margin-top 0.2rem
  line-height 0.44rem
  text-text-indent 0.2rem
  background #fff
  font-size 0.4rem
  padding 0.24rem 0 0.26rem
  height 0.44rem
  .title-img
    display inline-block
    width 0.3rem
    height 0.3rem
    margin-left 0.2rem
    vertical-align top
.item
  display flex
  height 1.8rem
  overflow hidden
  .item-img
    width 1.6rem
    height 1.6rem
    padding 0.1rem
  .item-info
    flex 1
    padding 0.1rem
    min-width 0
    .item-title
      line-height 0.54rem
      font-size 0.32rem
      ellipsis()
    .item-desc
      line-height 0.4rem
      color #ccc
      ellipsis()
    .item-button
      line-height 0.44rem
      margin-top 0.16rem
      background #ff9300
      padding 0 0.1rem
      border-radius 0.06rem
      color #fff
</style>
