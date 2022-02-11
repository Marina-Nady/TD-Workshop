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
</template>

<script>
import axios from "axios";
import Swiper, { Navigation } from 'swiper';
Swiper.use([Navigation]);
import 'swiper/swiper-bundle.css';

export default {
  name: 'Swiper',
  props: {
    options: {
      type: Object,
      default: () => {
        return {
          slidesPerView: 1
        }
      }
    }
  },
  data() {
    return {
      swiper: null,album:[]
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

      this.swiper = new Swiper('.swiper', {
        slidesPerView: this.options.slidesPerView,
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
</style>
