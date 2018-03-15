<template>
    <div class="slider" ref="slider">
      <div class="slider-group" ref="sliderGroup">
        <slot>
        </slot>
      </div>
  </div>
</template>

<script type="text/ecmascript-6">

  import BScroll from 'better-scroll'
  import {addClass} from 'common/js/dom'
  export default {
    name: 'slider',
    props: {
      loop: {
        type: Boolean,
        default: true
      },
      autoPlay: {
        type: Boolean,
        default: true
      },
      interval: {
        type: Number,
        default: 2000
      }
    },
    data() {
      return {
        currentPageIndex: 0
      }
    },
    mounted() {
      setTimeout(() => {
        this._setSliderWidth()
        this._initSlider()
        if (this.autoPlay) {
          this._play()
        }
      }, 20)
    },
    methods: {
      _setSliderWidth() {
        this.children = this.$refs.sliderGroup.children
        let width = 0
        let sliderWidth = this.$refs.slider.clientWidth
        for (let i = 0; i < this.children.length; i++) {
          let child = this.children[i]
          addClass(child, 'slider-item')

          child.style.width = sliderWidth + 'px'
          width += sliderWidth
          this.$refs.sliderGroup.style.width = width + 'px'
        }
      },
      _initSlider() {
        this.slider = new BScroll(this.$refs.slider, {
          scrollX: true,
          scrollY: false,
          momentum: false,
          snap: true,
          snapLoop: this.loop,
          snapThreshold: 0.3,
          snapSpeed: 400
        })
      },
      _play() {
        let pageIndex = this.currentPageIndex + 1
        if (this.loop) {
          pageIndex += 1
        }
        this.timer = setTimeout(() => {
          this.slider.goToPage(pageIndex, 0, 400)
        }, this.interval)
      }
    }
  }
</script>

<style type="text/css" lang="less" scoped>
  .slider {
    min-height: 1px;
    height: 100px;
    .slider-group {
      position: relative;
      overflow: hidden;
      white-space: nowrap;
      height: 100px;
      .slider-item {
        float: left;
        height: 100px;
        box-sizing: border-box;
        overflow: hidden;
        text-align: center;
        a {
          display: block;
          width: 100%;
          height: 100%;
          overflow: hidden;
          text-decoration: none;
          img {
            width: 100%;
            height: 100%;
          }
        }
      }
    }
  }
</style>