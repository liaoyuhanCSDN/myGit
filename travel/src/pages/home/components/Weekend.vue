<template>
   <div>
    <div class="title">
        周末去哪
    </div>
    <ul>
        <li class="item border-bottom" v-for="item of imgList" :key="item.id">
            <div class="item-img-wrapper">
              <img class="item-img" :src="item.imgUrl" >
            </div>
            <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
            </div>
        </li>
    </ul>
   </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
      return {
          imgList : [{
               id: '0001',
               imgUrl: 'http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          },{
               id: '0002',
               imgUrl: 'http://img1.qunarzz.com/sight/source/1606/88/56f7f4bd0493fe.jpg_r_640x214_f8c0994a.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          },{
                id: '0003',
               imgUrl: 'http://img1.qunarzz.com/sight/source/1505/50/07fa9343791682.jpg_r_640x214_c8c3d798.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          },
          {
                id: '0004',
               imgUrl: 'http://img1.qunarzz.com/sight/source/1505/ec/902725c4d56517.jpg_r_640x214_7a74d251.jpg',
               title: '长隆野生动物世界',
               desc:'长隆野生动物世界'
          },
          {
               id: '0005',
               imgUrl: 'http://img1.qunarzz.com/sight/source/1505/6f/bf9ef732f8ad2e.jpg_r_640x214_c759559e.jpg',
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
      .item-img-wrapper
        overflow : hidden
        height : 0
        padding-bottom : 33%
       .item-img
         width : 100%
       .item-info
         padding : .1rem .2rem
         color : #212121
         font-size :.32rem
         min-width : 0
         line-height :.56rem     
         .item-title
             ellipsis()
         .item-desc
             ellipsis()
                     
</style>
