<template>
  <div class="m-header">
      <a href="" class="m-header-left  iconfont icon-fanhui"></a>
      <div class="m-header-title">
          <i class="m-header-search iconfont icon-2fangdajing"></i>
          <span class="mp-single-line">输入城市/景点/游玩主题</span>
      </div>
      <div class="m-header-right">
          <span class="m-header-location">北京</span>
          <i class="iconfont icon-xiajiantou"></i>
      </div>
  </div>
</template>

<script type="text/ecmascript-6">
    export default {
    }
</script>

<style type="text/css" lang="less" scoped>
    .m-header {
        overflow: hidden;
        height: 44px;
        background: #00bcd4;
        .m-header-left {
            padding-left: 10px;
            float: left;
            height: 44px;
            width: 30px;
            font-size: 24px;
            color:#fff;
            line-height: 44px;
            
        }
        .m-header-title {
            margin-top: 7px;
            float: left;
            width:210px;
            height: 30px;
            color:#e4e7ea;
            background: #fff;
            border-radius: 4px;
            .m-header-search {
                padding: 0 5px;
                float:left;
                width: 20px;
                height: 30px;
                line-height: 30px;
                font-size: 18px;
                font-weight: 900;
            }
            .mp-single-line {
                height: 30px;
                font-size: 14px;
                line-height: 30px;
                font-weight: 900;
            }

        }
        .m-header-right {
            padding-left: 5px; 
            float: left;
            width:64px;
            height: 44px;
            font-weight: 900;
            color: #fff;
            line-height: 44px;
        }
    }
</style>