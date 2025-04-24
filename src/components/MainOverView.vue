<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import { Pagination, Navigation } from 'swiper/modules'

const { subtitle, title } = defineProps({
  subtitle: String,
  title: String
})

const modules = [Pagination, Navigation];

const itemList = [
  { itemName: "락시크 워싱 절개 레더 자켓", itemText: "최근 유행하고 있는 락시크 스타일의 어쩌고 저쩌고", itemImage: "test.jpg", itemPrice: "85,500원", itemSrc: "", coordiImage: "" },
  { itemName: "클락 피셔맨 데일리 라운드 티셔츠", itemText: "최근 유행하고 있는 락시크 스타일의 어쩌고 저쩌고", itemImage: "test.jpg", itemPrice: "85,500원", itemSrc: "", coordiImage: "" },
  { itemName: "커브드 와이드 라인 데님 팬츠", itemText: "최근 유행하고 있는 락시크 스타일의 어쩌고 저쩌고", itemImage: "test.jpg", itemPrice: "85,500원", itemSrc: "", coordiImage: "" },
  { itemName: "락시크 무드 지퍼 첼시 부츠", itemText: "최근 유행하고 있는 락시크 스타일의 어쩌고 저쩌고", itemImage: "test.jpg", itemPrice: "85,500원", itemSrc: "", coordiImage: "" },
  { itemName: "오늘 출발", itemText: "최근 유행하고 있는 락시크 스타일의 어쩌고 저쩌고", itemImage: "test.jpg", itemPrice: "85,500원", itemSrc: "" },
  { itemName: "오늘 출발", itemText: "최근 유행하고 있는 락시크 스타일의 어쩌고 저쩌고", itemImage: "test.jpg", itemPrice: "85,500원", itemSrc: "" },
  { itemName: "오늘 출발", itemText: "최근 유행하고 있는 락시크 스타일의 어쩌고 저쩌고", itemImage: "test.jpg", itemPrice: "85,500원", itemSrc: "" },
  { itemName: "오늘 출발", itemText: "최근 유행하고 있는 락시크 스타일의 어쩌고 저쩌고", itemImage: "test.jpg", itemPrice: "85,500원", itemSrc: "" },
]
</script>

<template>
  <div class="gridOn">
    <div class="titleLine mb-6">
      <span class="d-block mb-1" style="font-size: 18px;">{{subtitle}}</span>
      <h1 style="font-size: 25px;">{{title}}</h1>
    </div>
    <div class="overView d-flex justify-space-between">

      <div class="imagePannel" style="height: 500px;">
        <img src="/img/test.jpg" class="w-100 h-100 d-block bg-black" alt="No Image" style="border-radius: 8px;">
      </div>

      <div class="itemPannel d-flex flex-column justify-space-between">
        <div class="contents">
          <h1 class="itemTitle">겨울 락시크 코디 조합</h1>
          <p class="itemSubtitle mt-2">추운 겨울에도 감성과 무드를 포기할 수 없는 분들을 위한 락시크 조합입니다.</p>
        </div>

        <Swiper :slidesPerView="4" :spaceBetween="20" :navigation="true" :pagination="{
          clickable: true,
        }" :modules="modules" class="mySwiper w-100" :loop="true">

          <SwiperSlide v-for="(item, i) in itemList" :key="i" elevation="4">
            <img :src="'img/' + item.itemImage" alt="No Image" class="w-100 d-block bg-black"
              style="height: 280px; border-radius: 8px;">
            <div class="itemText mt-4">
              <h3 style="font-size: 17px;" class="nameLineOne">{{ item.itemName }}</h3>
              <p style="font-size: 15px; color: #6b6b6b;" class="mt-2 mb-4 textLineOne">{{ item.itemText }}</p>
            </div>

            <div class="itemInfo d-flex justify-space-between align-center">
              <h4 style="font-size: 20px;">{{ item.itemPrice }}</h4>
              <v-button>❤️</v-button>
            </div>
          </SwiperSlide>

        </Swiper>
      </div>

    </div>
  </div>
</template>

<style scoped>

.mySwiper:deep(.swiper-button-next::after),
.mySwiper:deep(.swiper-button-prev::after){
  font-weight: 900;
    color: white !important;
    background-color: #00000055;
    padding: 12px;
    border-radius: 8px;
    font-size: 22px !important;
}
.imagePannel {
  width: calc((100% / 12) * 4 - 10px);
}

.itemPannel {
  width: calc((100% / 12) * 8 - 10px);
}

.nameLineOne,
.textLineOne {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
}
</style>
