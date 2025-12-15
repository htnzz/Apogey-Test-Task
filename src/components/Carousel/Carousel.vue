<template>
  <Swiper
    :modules="[Navigation, Pagination, Autoplay]"
    :slides-per-view="1"
    :loop="true"
    :speed=2500
    :autoplay="{ delay: 5000 }"
    :allow-touch-move="false"
    class="carousel-swiper"
  >
    <SwiperSlide>
      <div class="slide">
        <img src="@/assets/img/main_slide_1.jpg" />
        <div class="slide-overlay"></div>
      </div>
    </SwiperSlide>

    <SwiperSlide>
      <div class="slide">
        <img src="@/assets/img/main_slide_2.jpg" />
        <div class="slide-overlay"></div>
      </div>
    </SwiperSlide>

    <SwiperSlide>
      <div class="slide">
        <img src="@/assets/img/main_slide_3.jpg" />
        <div class="slide-overlay"></div>
      </div>
    </SwiperSlide>
  </Swiper>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation, Pagination, Autoplay } from 'swiper/modules'


import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import '@/components/Carousel/Carousel.css'
</script>
