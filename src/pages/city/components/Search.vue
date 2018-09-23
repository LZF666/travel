<template>
  <div>
    <div class="search">
      <input type="text" name="" id="search-input" placeholder="输入城市名或拼音" v-model="keyword">
    </div>
    <div class="search-content">
      <ul>
        <li v-for="item of list" :key="item.id">{{item.name}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CitySearch',
  prpos: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword > -1) || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.search
  height 0.72rem
  padding 0 0.1rem
  background $bgColor
  #search-input
    box-sizing border-box
    width 100%
    height 0.62rem
    line-height 0.62rem
    text-align center
    border-radius 0.06rem
    color #666
    padding 0 0.1rem
.search-content
  z-index 1
  overflow hidden
  position absolute
  top 1.58rem
  left 0
  right 0
  bottom 0
  background green
</style>
