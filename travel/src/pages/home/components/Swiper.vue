<template>
   <div  class="wrapper">
    <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="item of swiperList"  :key="item.id">
         <img class="swiper-img" :src="item.imgUrl"/>
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1802/d1/af067e81b43fe02.jpg_750x200_d2499d48.jpg'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/7c/2c4d68edbe30dd02.jpg_750x200_a49ba03d.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
   .wrapper >>> .swiper-pagination-bullet-active
    background :#fff !important
   .wrapper
     overflow :hidden
     width :100%
     height :0
     padding-bottom :26.25%
     background :#eee
     .swiper-img
       width : 100%
</style>
