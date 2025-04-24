<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const rankItem = [
  { rankCount: '1', rankContent: '반팔티' },
  { rankCount: '2', rankContent: '가디건' },
  { rankCount: '3', rankContent: '오늘 출발' },
  { rankCount: '4', rankContent: '슬랙스' },
  { rankCount: '5', rankContent: '첼시부츠' },
];

const currentIndex = ref(0);
let intervalId = null;

onMounted(() => {
  intervalId = setInterval(() => {
    currentIndex.value = (currentIndex.value + 1) % rankItem.length;
  }, 3000);//테스트햣
});

onBeforeUnmount(() => {
  clearInterval(intervalId);
});
</script>

<style scoped>
.menuOne,
.menuTwo,
.menuThree {
  width: 18px;
  height: 2.5px;
  display: block;
  background-color: black;
  border-radius: 1000px;
  margin: 4px 0;
}

.hot {
  font-weight: 900;
  color: red;
}

.line {
  display: block;
  width: 1.5px;
  height: 70%;
  background-color: #d9d9d9;
  border-radius: 1000px;
}

.searchIcon {
  position: absolute;
  top: 50%;
  right: 12px;
  transform: translateY(-50%);
}

.rank {
  height: 36px;
  overflow: hidden;
  position: relative;
}

.rank-inner {
  transition: transform 0.5s ease-in-out;
  transform: translateY(calc(-36px * var(--current-index)));
}

.rank li {
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}
</style>

<template>
  <div class="headerMenu d-flex justify-space-between align-center pb-4">
    <div class="menuSection d-flex">
      <div class="burgerMenu mr-7">
        <span class="menuOne"></span>
        <span class="menuTwo"></span>
        <span class="menuThree"></span>
      </div>

      <ul class="depthMenu pa-0 ma-0 d-flex align-center">
        <li class="mr-4 c-point">이벤트</li>
        <li class="mr-4 c-point hot">SALE</li>
        <li class="mr-4 c-point">베스트</li>
        <li class="mr-4 line"></li>
        <li class="mr-4 c-point">상의</li>
        <li class="mr-4 c-point">하의</li>
        <li class="mr-4 c-point">신발</li>
        <li class="mr-4 c-point">악세사리</li>
        <li class="mr-4 line"></li>
        <li class="mr-4 c-point">코디</li>
        <li class="mr-4 c-point">커뮤니티</li>
        <li class="mr-4 c-point">고객센터</li>
        <li>고객센터</li>
      </ul>
    </div>

    <div class="searchSection d-flex align-center">
      <ul class="rank pa-0 mr-3">
        <div
          class="rank-inner"
          :style="{ '--current-index': currentIndex }"
        >
          <li
            v-for="(item, i) in rankItem"
            :key="i"
          >
            <b class="d-block mr-3">{{ item.rankCount }}.</b>
            <p style="width: 140px;">{{ item.rankContent }}</p>
          </li>
        </div>
      </ul>

      <div class="searchBox position-relative">
        <input
          type="text"
          width="166"
          height="30"
          placeholder="'발마칸 코트'를 검색하세요"
        />
        <img
          src="/img/Search.svg"
          alt="No Icon"
          class="searchIcon"
          width="13"
          height="13"
        >
      </div>
    </div>
  </div>
</template>
