<template>
    <div v-if="options" ref="swiper" class="swiper">
    <div class=" swiper-wrapper">
      <div
        v-for="image in album"
        :key="image.id"
        class="swiper-slide"
      >
        <img v-bind:src='image.url' style="width:100%;height:auto"/>
      </div>
    </div>
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
  </div>

  <div ref="thumbnail" class="thumbnail">
      <div class=" swiper-wrapper">
      <div
        v-for="image in album"
        :key="image.id"
        class="swiper-slide"
      >
        <img v-bind:src='image.thumbnailUrl'/>
      </div>
    </div>
  </div>  
</template>

<script>

import axios from "axios";
import Swiper, { Navigation,Thumbs } from 'swiper';
Swiper.use([Navigation,Thumbs]);
import 'swiper/swiper-bundle.css';

export default {
  name: 'Swiper',
  props: {
    options: {
      type: Object,
      default: () => {
        return {
           slidesPerView: 1,slidesThumb: 4
        }
      }
    }
  },
  data() {
    return {
      swiper: null,thumbnail:null,album:[]
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/photos?albumId=1').then((result) => {
        this.album = result.data
    })
  },
  mounted() {
    let vm = this;
    if (this.options && vm.$refs.swiper !== 'undefined') {
        this.thumbnail = new Swiper('.thumbnail', {
        breakpoints: {
          320: {
            slidesPerView: 2,
            spaceBetween: 10
          },
          800: {
            slidesPerView: 3,
            spaceBetween: 30
          },
          900: {
            slidesPerView: this.options.slidesThumb,
            spaceBetween: 20
          }

        },
        slideThumbActiveClass	:'.swiper-slide-thumb-active',
        freeMode: true,
        watchSlidesVisibility: true,
        watchSlidesProgress: true,
      });
      this.swiper = new Swiper('.swiper', {
        slidesPerView: this.options.slidesPerView,
        spaceBetween:10,
        thumbs: {
          swiper: this.thumbnail
        },
        thumbsContainerClass	:'.swiper-thumbs',
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
        on: {
          init: function () {
            console.log('swiper initialized');
          },
          resize: function () {
            console.log('resize');
          }
        }
      });
    }
  },
  methods: {
  }
};

</script>

<style scoped>

.swiper{
	width: 50%;
	margin: auto;
  border-radius: 15px;
}
.swiper .swiper-wrapper .swiper-slide{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 20rem;
}
.thumbnail {
    width: 60%;
    margin: 2rem auto;
    overflow: hidden;
}
.thumbnail .swiper-wrapper .swiper-slide img{
    border-radius: 15px;
    width:100%;
    height: 7rem;
}
.thumbnail .swiper-wrapper .swiper-slide-thumb-active {
    background: #000;
    border-radius: 15px;
}
.thumbnail .swiper-wrapper .swiper-slide-thumb-active img{
  opacity: 0.5;
}
   @media (max-width: 700px) {
.swiper .swiper-wrapper .swiper-slide{
    height: 5rem;
}
.thumbnail .swiper-wrapper .swiper-slide img{
  height: auto;
  }
  .thumbnail {
    margin: 2rem auto 0 auto;
}
    }

</style>
