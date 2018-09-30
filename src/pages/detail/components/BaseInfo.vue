<template>
<div>
  <div class="baseInfo" v-for="(item, index) of baseInfo" :key="index">
    <div class="baseInfo-first" border-bottom>
      <div class="comment">
        <a href="#" class="baseInfo-link">
          <div>
            <span class="score">{{item.score}}</span>
            <span class="score-text">分</span>
            <span class="comment-desc">{{item.commentDesc}}</span>
          </div>
          <div>
            <span class="totalCommentNum">31098条评论</span>
            <span class="totalCommentNum">89条攻略</span>
            <span class="iconfont" id="detail-next-icon">&#xe66b;</span>
          </div>
        </a>
      </div>
      <div class="sight-desc">
        <a href="#" class="baseInfo-link">
          <div>
            <span class="sight-title">景点简介</span>
          </div>
          <div>
            <span class="sight-text">开放时间、贴士</span>
            <span class="iconfont" id="detail-next-icon">&#xe66b;</span>
          </div>
        </a>
      </div>
    </div>
    <div class="address">
      <p class="address-text">
        <span class="iconfont" id="detail-address-icon">&#xe633;</span>
        {{item.address}}
        <span class="iconfont" id="address-next-icon">&#xe66b;</span>
      </p>
    </div>
  </div>
</div>
</template>
<script>
export default {
  name: 'BaseInfo',
  props: {
    baseInfo: Array
  }
}
</script>
<style lang="stylus" scoped>
.baseInfo
  position relative
  top -0.1rem
  padding 0.1rem 0.2rem 0 0.2rem
  margin-bottom 0.1rem
  background #ffffff
  border-radius 0.1rem 0.1rem 0 0
  border-bottom 0.2rem solid #eee
  .baseInfo-first
    padding-top 0.1rem
    padding-bottom 0.2rem
    display flex
    width 100%
    height 100%
    border-bottom 0.5px solid #eee
    .comment
      position relative
      flex 1
      .baseInfo-link
        position absolute
        left 0
        top 0
        width 100%
        height 100%
        .score
          font-size 0.44rem
          color #ff8300
          line-height 0.44rem
        .score-text
          font-size 0.28rem
          color #ff8300
          line-height 0.48rem
        .comment-desc
          color #ff8300
          font-size 0.28rem
          line-height 0.48rem
          margin-left 0.2rem
        .totalCommentNum
          font-size 0.24rem
          color #9e9e9e
          line-height 0.32rem
          margin-right 0.2rem
        .totalCommentText
          color #9e9e9e
          font-size 0.24rem
          line-height 0.32rem
          margin-right 0.2rem
    .sight-desc
      position relative
      flex 1
      .sight-title
        font-size 0.28rem
        color #212121
        line-height 0.48rem
        padding-left 0.3rem
    .sight-text
      color #9e9e9e
      font-size 0.24rem
      padding-left 0.3rem
  .address
    position relative
    padding 0.2rem 0
    line-height 0.36rem
    color #212121
    .address-text
      padding-right 0.56rem
      position relative
      padding-left 0.56rem
#detail-next-icon
  position absolute
  top 0.3rem
  right 0.2rem
  color #9e9e9e
  font-size 0.24rem
  transform rotate(180deg)
#address-next-icon
  position absolute
  top 50%
  right 0
  margin-top -0.14rem
  color #9e9e9e
  font-size 0.24rem
  transform rotate(180deg)
#detail-address-icon
  height 100%
  line-height 100%
  position absolute
  left 0
  top 50%
  margin -0.17rem 0.2rem 0 0
  color #9e9e9e
  font-size 0.36rem
.baseInfo:after
  display block
  content ''
  background #eee
  height 1px
  width 100%
</style>
