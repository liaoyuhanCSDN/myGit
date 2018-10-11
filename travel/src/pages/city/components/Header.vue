<template>
    <div>
        <router-link to="/">
            <div class="header">
                <div class="iconfont header-icon">&#xe624;</div>   
                城市选择
            </div>
        </router-link>
    </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
     @import '~styles/varibles.styl';
     @import '~styles/mixins.styl'
    .header
        position : relative
        height : $headerHeight
        line-height : $headerHeight
        color : #fff
        text-align :center
        font-size :.32rem
        background :$bgColor
        .header-icon
           position : absolute
           top : 0
           left : 0
           color : #fff
           width : .64rem
           text-align : center
           font-size :.3rem
</style>
