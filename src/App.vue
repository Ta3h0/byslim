<script setup>
import HeaderVue from './Header/Header.vue'
import MainBannerOne from './Components/MainBannerOne.vue'
import HomeMenu from './components/HomeMenu.vue';
import MainOverView from './components/MainOverView.vue';
import NewArrival from './components/NewArrival.vue';
import SlideBar from './components/SlideBar.vue';

console.log("hi");
</script>

<style scoped>
.header {
  border-bottom: 1px solid #d9d9d9;
}
</style>

<template>
  <div>
    <HeaderVue />
    <MainBannerOne />
    <HomeMenu />
    <section>
      <SlideBar subtitle="가장 인기있는" title="WEEKLY BEST" :likeOn="true"/>
    </section>
    <section>
      <MainOverView subtitle="오늘 뭐 입지?" title="OUTFIT OF THE DAY"/>
    </section>
    <section>
      <NewArrival subtitle="트렌드를 반영하는" title="NEW ARRIVAL" />
    </section>
    <section>
      <SlideBar subtitle="에디터가 선택한" title="MD’s PICK" :likeOn="true" />
    </section>
    <section>
      <SlideBar subtitle="검색량이 많은" title="‘발마칸 코트’ 아이템 모음"  :likeOn="true" />
    </section>
    <!-- <router-view /> -->
  </div>
</template>