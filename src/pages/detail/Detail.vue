<template>
  <div>
    <detail-banner :sightName="sightName" :bannerImg="bannerImg" :bannerImgs="gallaryImgs"></detail-banner>
    <detail-header></detail-header>
    <base-info :baseInfo="baseInfo"></base-info>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>
<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import BaseInfo from './components/BaseInfo'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList,
    BaseInfo
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: [],
      baseInfo: []
    }
  },
  methods: {
    getDetailInfo () {
      let id = this.$route.params.id
      axios.get('/api/detail' + id + '.json', {
        params: {
          id: id
        }
      }).then(this.handleGetDataSucc)
    },
    handleGetDataSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.categoryList
        this.baseInfo = data.baseInfo
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>
<style lang="stylus" scoped>
.content
  height 50rem
</style>
