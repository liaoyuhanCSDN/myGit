<template>
       <ul class="list">
            <li class="item"  
               v-for="item of letters" 
               :key="item"
               :ref="item"
               @click="handleLetterClick"
               @touchstart="handleTouchStart"
               @touchmove="handleTouchMove"
               @touchend="handleTouchEnd"
           >
               {{item}}
           </li>
       </ul>
</template>

<script>
export default {
   name: 'CityAlphabet',
   props: {
       cities: Object
   },
   data () {
       return {
           touchStatus: false,
           startY: 0,
           timer: null
       }
   },
   updated () {
       this.startY = this.$refs['A'][0].offsetTop
   },
   methods: {
       handleLetterClick (e) {
           this.$emit('change',e.target.innerText)
       },
       handleTouchStart () {
           this.touchStatus = true
       },
       handleTouchMove (e) {
             if (this.touchStatus) {

                 if (this.timer) {
                     clearTimeout(this.timer)
                 }
                 this.timer = setInterval(() => {
                    const touchY = e.touches[0].clientY - 74 
                    const index =  Math.floor((touchY - this.startY) / 20) 
                    if (index >= 0 && index < this.letters.length) {
                        this.$emit('change',this.letters[index])
                    }
                 },16)
             }
       },
       handleTouchEnd () {
          this.touchStatus = false
       }
   },
   computed: {
       letters () {
           const letter = []
           for (let i in this.cities) {
               letter.push(i)
           }
           return letter
       }
   }
}
</script>

<style lang="stylus" scoped>
      @import '~styles/varibles.styl'
      @import '~styles/mixins.styl'
      .list
       display : flex
       flex-direction : column
       justify-content : center
       position : absolute
       top : 1.58rem
       width : .4rem
       right : 0
       bottom : 0
       line-height : .4rem
       text-align : center
       .item
         color : $bgColor
       
</style>
