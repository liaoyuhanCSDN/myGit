<template>
   <div>
    <div class="title">
        热销推荐
    </div>
    <ul>
        <li class="item border-bottom" v-for="item of imgList" :key="item.id">
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
  data () {
      return {
          imgList : [{
               id: '0001',
               imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_200x200_ea02ef99.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          },{
               id: '0002',
               imgUrl: 'http://img1.qunarzz.com/sight/p0/1810/a0/a021cde25761c0aa3.img.jpg_200x200_7635f5ba.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          },{
                id: '0003',
               imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/71/71daa558cbccbb92a3.img.jpg_200x200_133f9dec.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          },
          {
                id: '0004',
               imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_200x200_b902dd9e.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          },
          {
               id: '0005',
               imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_200x200_c118d7da.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          }
          ]
      }
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
