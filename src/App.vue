<template>
  <div id="app">
    <vue-smart-swiper ref="swiper_1" id="swiper_1" style="  width: 100%;height: 300px;" :pagination="true" :button="true" :option="{effect : 'fade',autoplay:{
      delay:3000,
    },navigation: {
    nextEl: '.swiper-button-next',
    prevEl: '.swiper-button-prev',
  },
  on: {
    slideChange: function(){
      if(this.isEnd){
        this.navigation.$nextEl.css('display','none');
      }else{
        this.navigation.$nextEl.css('display','block');
      }
      if(this.isBeginning){
        this.navigation.$prevEl.css('display','none');
      }else{
        this.navigation.$prevEl.css('display','block');
      }
    },
  },
    }">
      <div class="swiper-slide" style="background: red">Slide 1</div>
      <div class="swiper-slide" style="background: yellow">Slide 2</div>
      <div class="swiper-slide" style="background: pink">Slide 3</div>
      <div class="swiper-slide" style="background: #ccc">Slide 4</div>
    </vue-smart-swiper>


  </div>
</template>

<script>
  import fastclick from 'fastclick'
  import VueSmartSwiper from "vue-smart-swiper"

export default {
    components:{VueSmartSwiper},
  name: 'app',
  data () {
    return {

    }
  },
  mounted: function () {

    fastclick.attach(this.$el)
    this.$nextTick(function () {
      console.log(this.$refs.swiper_1.swiper)
    })
  }
}
</script>

<style>
@import "assets/css/base.css";
@import "assets/css/mobile_h5.css";
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
  .swiper-slide{
    text-align: center;line-height: 300px;
  }
</style>
