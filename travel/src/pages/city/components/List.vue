<template>
    <div class="list" ref="wrapper">
        <div>
         <div class="area">
             <div class="title border-topbottom">您的位置</div>
             <div class="button-list">
                  <div class="button-wrapper">
                      <div class="button">北京</div>
                  </div>
                  <div class="button-wrapper">
                      <div class="button">北京</div>
                  </div>
                  <div class="button-wrapper">
                      <div class="button">北京</div>
                  </div>
                  <div class="button-wrapper">
                      <div class="button">北京</div>
                  </div>
                  <div class="button-wrapper">
                      <div class="button">北京</div>
                  </div>
             </div>
         </div>
         <div class="area">
             <div class="title border-topbottom">热门城市</div>
             <div class="button-list">
                  <div class="button-wrapper" v-for="item of list" :key="item.id">
                      <div class="button">{{item.name}}</div>
                  </div>
             </div>
         </div>
         <div 
             class="area" 
             v-for="(item,key) of cities" 
             :key="key"
             :ref="key"
         >
             <div class="title border-topbottom">{{key}}</div>
             <div class="area-title">
                <div class="area-content border-bottom" v-for="innerItem of item" :key="innerItem.id">{{innerItem.name}}</div>
             </div>
         </div>
        </div> 
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
    name: 'CityList',
    props: {
        list: Array,
        cities: Object,
        letter: String
    },
    data () {
        return {
            
        }
    },
    methods: {
    
    },
    mounted () {
        this.scroll =  new Bscroll(this.$refs.wrapper)
    },
    watch: {
        letter () {
            const letter = this.$refs[this.letter][0]
            this.scroll.scrollToElement(letter)
        } 
    }
}
</script>

<style lang="stylus" scoped>
   .border-topbottom
       &:before
        background : #ccc
       &:after
        background : #ccc
   .border-bottom
       &:before
        background : #ccc
   .list
    overflow : hidden   
    position : absolute
    top : 1.58rem
    left : 0
    right : 0
    bottom : 0      
    .title 
        height: .56rem
        background : #eee
        line-height .56rem
        color :#666
        font-size : .24rem
        padding-left :.2rem
    .button-list
        overflow : hidden
        padding :.1rem .6rem .1rem .1rem
        .button-wrapper
            float : left 
            width : 33.33%
            .button
                margin : .1rem
                padding :.1rem 0
                text-align : center
                border : .02rem solid #ccc
                border-radius : .06rem
    .area-title
        .area-content
            line-height :.76rem
            padding-left : .2rem    
</style>
