<template>
  <div class="m-home">
    <div class="slider-wrapper" v-if="recommends.length" ref="sliderWrapper">
        <Slider>
            <div class="" v-for="item in recommends" :key="item.id" >
                <a href="#">
                    <img class="needsclick" :src="item.imgUrl" alt="">
                </a>
            </div>
        </Slider>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import Slider from 'base/slider/slider'
  import axios from 'axios'
  export default {
    data() {
      return {
        recommends: []
      }
    },
    components: {
      Slider
    },
    created() {
      this._getRecommend()
    },
    methods: {
      _getRecommend() {
        axios.get('/static/home/home-swiperInfo.json').then((res) => {
          if (res.data.ret) {
            this.recommends = res.data.homeSwiperInfoList
          }
        })
      }
    }
  }
</script>

<style type="text/css" lang="less" scoped>
    .slider-wrapper {
        position: relative;
        width: 100%;
        overflow: hidden;
        // overflow: hidden;

    }
</style>