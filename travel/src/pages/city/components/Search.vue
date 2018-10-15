<template>
    <div>
        <div class="search">
            <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音" />
        </div>
        <div class="search-content" v-show="this.keyword"  ref="search">
            <ul>
                <li v-for="item of list" :key="item.id" class="search-item border-bottom">{{item.name}}</li>
                <li class="search-item border-bottom" v-show="hasData">没有该地区</li>
            </ul>
        </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
   name: 'CitySearch',
   props: {
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
          if (!this.keyword) {
              this.list = []
              return 
          }
          this.timer = setTimeout(() => {
              const result = []
                for (let i in this.cities) {
                    this.cities[i].forEach((value) => {
                        if (value.spell.indexOf(this.keyword) > -1 ||
                            value.name.indexOf(this.keyword) > -1) {
                                 result.push(value)
                            }
                    })
                } 
                this.list = result
          },60)
       }
   },
   computed: {
      hasData () {
          return !this.list.length
      }
   },
   mounted () {
       this.scroll = new Bscroll(this.$refs.search)
   }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
   .search
      height : .72rem
      background : $bgColor
      padding :  0  .1rem
      .search-input
          box-sizing : border-box
          width : 100%
          padding : 0  .1rem
          text-align : center
          height : .62rem
          line-height : .62rem
          touch-action: none
          border-radius : .06rem
   .search-content
     z-index : 1
     overflow : hidden
     position : absolute
     top : 1.58rem
     left : 0
     right : 0
     bottom : 0
     background : #eee
     .search-item 
       line-height : .62rem
       padding-left : .2rem
       color : #666
       background : #eee
</style>
