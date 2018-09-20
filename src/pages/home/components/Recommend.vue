<template>
  <div>
    <div class="cut-off"></div>
    <ul>
      <div class="title">
        <img class="title-img" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt=""> 猜你喜欢
      </div>
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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl:
            'http://img1.qunarzz.com/sight/p0/1508/12/4e6170303c63bdb7070fb1987480afab.water.jpg_200x200_0775a71c.jpg',
          title: '杭州极地海洋世界',
          desc: '模拟生态环境里与海洋动物亲密接触'
        },
        {
          id: '0002',
          imgUrl:
            'http://img1.qunarzz.com/sight/p0/1809/6b/6b0d71ae741a583da3.img.jpg_200x200_dc19cbb1.jpg',
          title: '杭州乐园',
          desc: '长三角地区新一代综合性主题公园'
        },
        {
          id: '0003',
          imgUrl:
            'http://img1.qunarzz.com/sight/p0/1603/ae/aecef86d7655873f90.water.jpg_200x200_22a0790e.jpg',
          title: '杭州野生动物世界',
          desc: '多功能综合性生态公园'
        },
        {
          id: '0004',
          imgUrl:
            'http://img1.qunarzz.com/sight/p0/201301/16/5e3b1c2e19e8d4c693835fbb.jpg_200x200_93a8fd7f.jpg',
          title: '龙井峡漂流',
          desc: '🔥好评如潮，小伙伴热推景点~'
        },
        {
          id: '0005',
          imgUrl:
            'http://img1.qunarzz.com/sight/p0/1603/57/57ee153a3441d35190.water.jpg_200x200_6626a45a.jpg',
          title: '杭州飞来峰',
          desc: '江南少见的古代石窟艺术瑰宝'
        }
      ]
    }
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
  height .44rem
  .title-img
    display inline-block
    width 0.3rem
    height 0.3rem
    margin-left .2rem
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
