<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import { Pagination, Navigation } from 'swiper/modules'

const modules = [Pagination, Navigation];
const bannerItem = [
  { src: "bannerBgOne.jpg", subtitle: "커플들을 위한", title: "프리사이즈 커플템 모음전", },
  { src: "bannerBgTwo.jpg", subtitle: "나를 생각한다면", title: "나의 가치를 올리다:: MD Pick", },
  { src: "bannerBgThree.jpg", subtitle: "고급스러움의 끝", title: "무드있는 아이템 모음전", },
  { src: "bannerBgFour.jpg", subtitle: "2025 Trend Category", title: "트렌드 카테고리 랭킹", },
  { src: "bannerBgFive.jpg", subtitle: "1+1 할인", title: "1 + 1 특급 할인전", },
  { src: "bannerBgOne.jpg", subtitle: "커플을 위한", title: "프리사이즈 커플템 모음전", },
  { src: "bannerBgTwo.jpg", subtitle: "나를 생각한다면", title: "나의 가치를 올리다:: MD Pick", },
  { src: "bannerBgThree.jpg", subtitle: "고급스러움의 끝", title: "무드있는 아이템 모음전", },
  { src: "bannerBgFour.jpg", subtitle: "2025 Trend Category", title: "트렌드 카테고리 랭킹", },
  { src: "bannerBgFive.jpg", subtitle: "1+1 할인", title: "1 + 1 특급 할인전", },
  { src: "bannerBgOne.jpg", subtitle: "커플을 위한", title: "프리사이즈 커플템 모음전", },
  { src: "bannerBgTwo.jpg", subtitle: "나를 생각한다면", title: "나의 가치를 올리다:: MD Pick", },
  { src: "bannerBgThree.jpg", subtitle: "고급스러움의 끝", title: "무드있는 아이템 모음전", },
  { src: "bannerBgFour.jpg", subtitle: "2025 Trend Category", title: "트렌드 카테고리 랭킹", },
  { src: "bannerBgFive.jpg", subtitle: "1+1 할인", title: "1 + 1 특급 할인전", },
];
</script>

<style scoped>
.mySwiper {
  height: 570px;
  padding: 40px 0;
}

.swiper-slide {
  position: relative;
  background-color: #d9d9d9;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  /* 은은한 그림자 */
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.swiper-slide::before {
  content: '';
  width: 100%;
  height: 100%;
  display: block;
  position: absolute;
  top: 0%;
  left: 0;
  background-color: #000;
  opacity: .7;
}

.swiper-slide-active::before,
.swiper-slide-prev::before,
.swiper-slide-next::before {
  display: none;
}

.swiper-slide .textBox2 {
  display: none;
}

.swiper-slide-prev .textBox2,
.swiper-slide-next .textBox2,
.swiper-slide-active .textBox2 {
  width: 100%;
  height: 27%;
  display: flex;
  position: absolute;
  bottom: 0%;
  left: 0;
  background: #000000;
  background: #000000;
  background: #000000;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.75) 57%, rgba(0, 0, 0, 0.22) 90%, rgba(255, 255, 255, 0) 98%);
  opacity: 1;
}

.nextBtn::after,
.prevBtn::after {
  font-weight: 900;
  color: #101010de !important;
  background-color: #ffffff;
  font-size: 22px !important;
  border: none;
  box-shadow: none;
}

.nextBtn::after {
  font-family: swiper-icons;
  content: 'next';
}

.prevBtn::after {
  font-family: swiper-icons;
  content: 'prev';
}

.btnArea {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: calc(25% * 3 - 34px);
  z-index: 1;
}

.custom-pagination {
  background-color: #d9d9d9 !important;
}
.custom-pagination:deep(.swiper-pagination-progressbar-fill) {
  background-color: #222 !important;
}
</style>

<template>
  <div class="position-relative">
    <Swiper :slidesPerView="4" :centeredSlides="true" :spaceBetween="20" :slidesPerGroup="3" :initialSlide="3"
      :speed="600" :pagination="{
        el: '.custom-pagination',
        type: 'progressbar',
      }" :modules="modules" class="mySwiper px-5" :loop="true"
      :navigation="{ nextEl: '.nextBtn', prevEl: '.prevBtn' }">

      <SwiperSlide v-for="(item, i) in bannerItem" :key="i" elevation="4">
        <img :src="'img/' + item.src" alt="No Image">
        <div class="textBox2 pb-5 text-white flex-column justify-end">
          <p class="text-body-3 px-5">{{ item.subtitle }}</p>
          <h1 class="my-2 px-5" style="height: 64px;">{{ item.title }}</h1>
        </div>
      </SwiperSlide>
    </Swiper>


    <div class="btnArea d-flex justify-end align-center">
      <div class="custom-pagination" style="width: calc(100% - 95px); top: 50%; transform: translateY(-50%); height: 4px;"></div>
      <div class="d-flex align-center">
        <button class="prevBtn largePrevBtn"></button>
        <span style="display: block; width: 2px; height: 15px; background-color: #d9d9d9;"></span>
        <button class="nextBtn largeNextBtn"></button>
      </div>
    </div>
  </div>
</template>  