<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import { Pagination, Navigation } from 'swiper/modules'
import { ref } from 'vue'

const { subtitle, title, discountOn, likeOn } = defineProps({
  subtitle: String,
  title: String,
  discountOn: Boolean,
  likeOn: Boolean,
})


const modules = [Pagination, Navigation];

const itemList = [
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },
  {
    itemName: "락시크 워싱 절개 레더 자켓",
    itemText: "최근 유행하고 있는 락시크 스타일의 레더 자켓에 자연스럽고 부드러운 워싱과 절개를 추가하여",
    itemImage: "test.jpg",
    itemPrice: "85,500원",
    originPrice: "95,000원",
    discountPer: "21%"
  },


]

</script>

<style scoped>
.textLineOne {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
}

.textLineTwo {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}

.itemImage {
  height: 250px;
  display: block;
  border-radius: 8px;
  background-color: #999;
}

.mySwiper:deep(.swiper-button-next::after),
.mySwiper:deep(.swiper-button-prev::after) {
  font-weight: 900;
  color: white !important;
  background-color: #00000055;
  padding: 12px;
  border-radius: 8px;
  font-size: 22px !important;
}
</style>

<template>
  <div class="gridOn">
    <div class="titleLine mb-6">
      <span class="d-block mb-1" style="font-size: 18px;">{{ subtitle }}</span>
      <h1 style="font-size: 25px;">{{ title }}</h1>
    </div>
    <Swiper :slidesPerView="6" :spaceBetween="20" :navigation="true" :pagination="{
      clickable: true,
    }" :modules="modules" class="mySwiper" :loop="true">

      <SwiperSlide v-for="(item, i) in itemList" :key="i" elevation="4">
        <img :src="'img/' + item.itemImage" alt="No Image" class="itemImage w-100">
        <div class="textBox d-flex flex-column justify-end">
          <h1 class="my-2 textLineOne" style="font-size: 18px;">{{ item.itemName }}</h1>
          <p class="mt-2 mb-3 textLineTwo text-body-2" style="line-height: 1 !important;">{{ item.itemText }}</p>
          <div class="priceArea d-flex justify-space-between w-100">
            <div class="d-flex align-end">
              <h4>{{ item.itemPrice }}</h4>
              <del style="color: #717171; margin-left: 4px; font-size: 12px;">{{ item.originPrice }}</del>
            </div>
            <h4 v-if="discountOn">{{ item.discountPer }}</h4>
            <p class="ma-0 pa-0" v-if="likeOn">❤️</p>
          </div>
        </div>
      </SwiperSlide>

    </Swiper>
  </div>
</template>