<template>
   <div>
    <div class="title">
        热销推荐
    </div>
    <ul>
        <li class="item border-bottom" v-for="item of list" :key="item.id">
            <img class="item-img" :src="item.imgUrl" >
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
  props: {
      list: Array
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/mixins.styl'
   .title
       margin-top : .2rem
       line-height :.8rem
       background : #ccc
       text-indent : .2rem
   .item
       overflow : hidden
       display : flex
       height :1.9rem
       .item-img
         box-sizing : border-box
         height : 100%
         padding : .1rem
       .item-info
         flex : 1
         padding : .1rem
         color : #212121
         font-size :.32rem
         min-width : 0
         .item-title
             ellipsis()
             line-height :.56rem
         .item-desc
             ellipsis()
             line-height :.56rem
         .item-button
             background :#cd9f7d      
               
</style>
