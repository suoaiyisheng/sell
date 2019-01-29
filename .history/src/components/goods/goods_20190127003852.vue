<template>
  <div class="goods">
    <div class="menu-wrapper"></div>
    <div class="foods-wrapper"></div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  props: {
    seller: {
      tyoe: Object
    }
  },
  created () {
    this.$http.get('/api/goods').then((response) => {

    })
  }
}
</script>

<style scoped lang="stylus">
.goods
  position  absolute
  top  174px
  bottom  46px
  display  flex
  width 100%
  overflow hidden
  .menu-wrapper
    flex 0 0 80px
    width 80px
    background #f3f5f7
  .foods-wrapper
    flex 1
</style>
