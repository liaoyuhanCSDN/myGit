<template>
    <div class="search">
        <input  class="search-input" type="text" placeholder="输入城市名或拼音" />
    </div>
</template>

<script>
export default {
   name: 'CitySearch'
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
</style>
