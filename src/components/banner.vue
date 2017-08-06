<template>
  <div>
    <slider class="slider" interval="3000" auto-play="true">
        <indicator class="indicator">
        </indicator>
            <div class="frame" v-for="(img,index) in imageList" :key="index">
                <image class="image" resize="cover" :src="img.src"></image>
            </div>
    </slider>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        imageList: [
          { src: 'https://gd2.alicdn.com/bao/uploaded/i2/T14H1LFwBcXXXXXXXX_!!0-item_pic.jpg'},
          { src: 'https://gd1.alicdn.com/bao/uploaded/i1/TB1PXJCJFXXXXciXFXXXXXXXXXX_!!0-item_pic.jpg'},
          { src: 'https://gd3.alicdn.com/bao/uploaded/i3/TB1x6hYLXXXXXazXVXXXXXXXXXX_!!0-item_pic.jpg'}
        ]
      }
    }
  }
</script>

<style scoped>
    .image {
        width: 700px;
        height: 700px;
    }
    .slider {
        margin-top: 25px;
        margin-left: 25px;
        width: 700px;
        height: 700px;
        border-width: 2px;
        border-style: solid;
        border-color: #41B883;
    }
    .frame {
        width: 700px;
        height: 700px;
        position: relative;
    }
    .indicator {
        width: 700px;
        height: 700px;
        item-color: #ffffff;
        item-selected-color: blue;
        item-size: 20px;
        position: absolute;
        top: 200px;
        left: 0px;
    }
</style>