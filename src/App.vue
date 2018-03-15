<template>
  <div id="app" @touchmove.prevent>
    <!-- <m-header></m-header> -->
    <m-home></m-home>
  </div>
</template>

<script type="text/ecmascript-6">
  import MHeader from 'components/m-header/m-header'
  import MHome from 'components/m-home/m-home'
  export default {
    components: {
      MHeader,
      MHome
    }
  }
</script>

<style type="text/css" lang="less" scoped>
  @import "common/fonts/iconfont.css";
</style>