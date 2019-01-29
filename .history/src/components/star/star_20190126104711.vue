<template>
 <div class="star" :class="starType">
   <span v-for="itemClass in itemClasses" :class="itemClass" class="star-item"></span>
 </div>
</template>

<script type="text/ecmascript-6">
const LENGTH = 5
const CLS_ON = 'on'
const CLS_HALF = 'half'
const CLS_OFF = 'off'

export default {
  props: {
    size: {
      type: Number
    },
    score: {
      type: Number
    },
    computed: {
      starType () {
        return 'star-' + this.size
      },
      itemClasses () {
        let result = []
        let score = Math.floor(this.score * 2) / 2
        let hasDecimal = score % 1 !== 0
        let integer = Math.floor(score)
        for (let i = 0; i < integer; i++) {
          result.push(CLS_ON)
        }
        if (hasDecimal) {
          result.push(CLS_HALF)
        }
        while (result.length < LENGTH) {
          result.push(CLS_OFF)
        }
        return result
      }
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
@import '../../common/stylus/minxin.styl'
  .star
    font-size: 0
    .star-item
      display: inline-block
      background-repeat: no-repeat
    &:last-child
        margin-right: 0
    &.star-48
      .star-item
        width 20px
        height 20px
        margin-right 22px
        background-size 20px 20p
        &.on
        bg-image('star48_on')
        &.half
        bg-image('star48_half')
        &.off
        bg-image('star48_offf')

</style>
